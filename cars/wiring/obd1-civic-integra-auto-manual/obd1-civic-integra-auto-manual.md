---
summary: 'Technical guide for converting OBD1 Honda ECUs between automatic and manual configurations via resistor board modifications.'
tags: [ecu, transmission, tuning, conversion, hardware, obd1]
applies_to:
  models: [civic, crx, del-sol, integra]
  chassis: [da, dc2, ef, eg, eg-eh]
complexity: advanced
---

# OBD1 ECU: Auto to Manual Conversion

USDM and JDM OBD1 Honda ECUs (e.g., P28, P30, P72, P06) share common hardware board layouts for both automatic and manual configurations. You can convert an automatic ECU for use in a manual transmission vehicle by modifying specific surface-mount resistor locations (**RP17** and **RP18**).

---

## Technical Overview
The ECU determines its transmission configuration by measuring resistance across two specific board locations: `RP17` and `RP18`. 

*   **Automatic Configuration:** Detected by the MCU via resistance on both `RP17` and `RP18`. Running an automatic ECU in a manual car without this conversion will trigger **Diagnostic Trouble Code 19** (Automatic Transmission Lockup Solenoid).
*   **Manual Configuration:** Achieved by jumpering `RP18` and leaving `RP17` empty, forcing the MCU to ignore automatic transmission control logic.

---

## Conversion Procedures

### 1. USDM Automatic to Manual
1.  Locate `RP17` and `RP18` on the lower right corner of the ECU circuit board.
2.  De-solder and remove both existing resistors.
3.  Install a solid jumper wire (or 0-Ohm resistor) in the `RP18` position.
4.  Leave the `RP17` position empty (open).

### 2. JDM Automatic to Manual
JDM small-case and large-case ECUs utilize a single resistor location for transmission configuration.
1.  Locate `RP18` on the back side of the board.
2.  De-solder and remove the factory 2.4k Ohm resistor.
3.  Install a **1.4k Ohm** resistor in its place.

### 3. USDM Manual to Automatic
If converting a manual ECU for automatic transmission support:
1.  Remove the `RP18` jumper.
2.  Install a **2.7k Ohm** resistor at `RP18`.
3.  Install a **4.7k Ohm** resistor at `RP17`.
4.  **Note:** You must also ensure the transmission solenoid driver transistor array (`IC16`, typically a `5050S` chip) is installed on the board.

---

## Technical Note
*Always verify your specific ECU part number, production region, and circuit board markings before soldering. Incorrect resistor values or improperly bridged pads can result in ECU failure or engine mismanagement.*
