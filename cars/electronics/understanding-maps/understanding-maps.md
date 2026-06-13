---
summary: 'An introductory guide explaining how fuel and ignition tables (maps) are structured and interpreted inside Honda ECU ROMs.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - tuning
  - rom
  - fueling
  - ignition
---

# Understanding ECU Fuel and Ignition Maps

Honda Engine Control Units (ECUs) utilize lookup tables—commonly referred to as maps—to control fuel injection duration and ignition timing advance. This guide explains how fuel and ignition tables are structured, how the ECU switches between operating modes, and how it interpolates values between cells to ensure smooth engine operation.

## Fuel Maps
For most driving conditions (typically below 80% throttle), the ECU operates in **closed-loop mode**. In this mode, the ECU uses feedback from the [oxygen sensor](/cars/electronics/oxygen-sensor) to constantly adjust the air-fuel ratio to a stoichiometric target (typically 14.7:1).

Once throttle position exceeds the closed-loop threshold, the ECU switches to **open-loop mode**. In open-loop mode, the ECU relies entirely on pre-programmed lookup tables (maps) to determine injector pulse-width:

![OBD0 ECU fuel map editor interface showing load columns and RPM rows](http://www.ef-honda.com/ben/pw0fuel.gif)

### Map Structure
- **Columns (Load/Vacuum):** The columns correspond to intake manifold pressure (vacuum/boost) measured by the manifold absolute pressure (MAP) sensor. The leftmost columns represent high vacuum (deceleration or idle), while the rightmost columns represent wide-open throttle (WOT).
  - OBD0 ECUs typically utilize 15 columns, measured in inches of mercury (inHg).
  - OBD1 ECUs utilize 10 columns, measured in millibars (mBar).
- **Rows (Engine Speed):** The rows represent engine speed in revolutions per minute (RPM).
- **Cells (Injector Pulse-width):** The values inside the cells represent the base injector duration, typically calculated in milliseconds. The ECU's tuning editor translates raw 8-bit hex values into human-readable pulse-widths using a specific multiplier formula (e.g., [OBD0 Fuel](/cars/electronics/obd0-fuel) or [OBD1 8-bit Fuel](/cars/electronics/obd1-8bit-fuel)).

## Ignition Maps
Like fuel delivery, ignition timing is determined via lookup tables:

![OBD0 ECU ignition map editor interface showing ignition advance in degrees](http://www.ef-honda.com/ben/pw0ignition.gif)

- **Columns and Rows:** The table structure mirrors the fuel maps, mapping engine speed (RPM) against intake manifold pressure.
- **Cells (Ignition Advance):** The cell values represent degrees of ignition advance before top dead center (BTDC).

## Map Interpolation
Because engine speed and load are continuous variables, the ECU rarely operates exactly on the coordinates of a single cell. To maintain smooth engine operation, the ECU performs **bilinear interpolation** to calculate the precise fuel or ignition value between the four surrounding cells.

The ECU calculates a weighted average of the surrounding cells using both the current MAP sensor reading and engine RPM.

### Step-by-Step Interpolation Example
Consider an engine operating at **5775 RPM** and **20 inHg** of manifold vacuum. 

Looking at the map above, the current state falls between:
- **Columns 3 and 4** (21 inHg and 19 inHg)
- **Rows 7 and 8** (5500 RPM and 6050 RPM)

The four surrounding cells provide the following values:
*   **Top-Left (3,7):** 21 inHg, 5500 RPM $\rightarrow$ **2.16 ms**
*   **Top-Right (4,7):** 19 inHg, 5500 RPM $\rightarrow$ **2.56 ms**
*   **Bottom-Left (3,8):** 21 inHg, 6050 RPM $\rightarrow$ **2.25 ms**
*   **Bottom-Right (4,8):** 19 inHg, 6050 RPM $\rightarrow$ **2.62 ms**

#### Step 1: Interpolate Column-Wise (Vacuum)
We calculate the weighted average between the load columns at the lower RPM row (Row 7) and upper RPM row (Row 8).

For Row 7 (5500 RPM) at 20 inHg (halfway between 21 and 19):
$$V_7 = \frac{21 - 20}{21 - 19} \times 2.16 + \frac{20 - 19}{21 - 19} \times 2.56 = (0.5 \times 2.16) + (0.5 \times 2.56) = 2.36\text{ ms}$$

For Row 8 (6050 RPM) at 20 inHg:
$$V_8 = \frac{21 - 20}{21 - 19} \times 2.25 + \frac{20 - 19}{21 - 19} \times 2.62 = (0.5 \times 2.25) + (0.5 \times 2.62) = 2.435\text{ ms}$$

#### Step 2: Interpolate Row-Wise (RPM)
Next, we interpolate between the two calculated RPM values ($V_7 = 2.36$ and $V_8 = 2.435$) for our target of 5775 RPM (halfway between 5500 and 6050 RPM):

$$\text{Final Value} = \frac{6050 - 5775}{6050 - 5500} \times 2.36 + \frac{5775 - 5500}{6050 - 5500} \times 2.435 = (0.5 \times 2.36) + (0.5 \times 2.435) = 2.3975\text{ ms}$$

The ECU will command an injector pulse-width of **2.3975 ms**.
