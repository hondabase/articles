---
summary: 'A detailed troubleshooting and repair guide for the Idle Air Control Valve (IACV) circuit on Honda OBD1 ECUs, specifically focusing on resistors R58, R59, and the Q21 driver transistor.'
tags: [ecu, repair, diagnostics, idle]
applies_to:
  obd: [1]
  brand: Honda
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eg-eh]
complexity: advanced
---

# IACV Circuit Fix - R58 and R59: Low Idle

A failed Idle Air Control Valve (IACV) driver circuit is a classic problem affecting Honda OBD1 Engine Control Units (ECUs) such as the P28, P06, P72, P30, and P75. When this circuit fails, the engine suffers from extreme idle issues and is unable to regulate target idle speed.

## Symptoms of a Burnt IACV Circuit

When the ECU's internal IACV control circuit is damaged, it typically exhibits the following symptoms:
1. **Persistent Check Engine Light (CEL) Code 14**: Idle Air Control Valve (IACV / EACV) malfunction. The code will return immediately even after clearing the ECU or replacing the physical valve.
2. **Extremely Low Idle**: The engine may idle at 200–400 RPM or stall completely unless the throttle is held open slightly.
3. **Surging or Bouncing Idle**: In some configurations, the idle may bounce repeatedly between 1000 and 1500 RPM.
4. **Physical ECU Damage**: Visual inspection of the ECU board reveals charred, smoked, or cracked resistors at locations **R58** and **R59**, and potentially a blown transistor at **Q21**.

---

## Root Cause: Swapped Connectors

The most common cause of this circuit blowout is a human wiring mistake during an engine swap or intake manifold reassembly. 

Because the engine wiring harness plugs for the **Intake Air Temperature (IAT) sensor** (or the Purge Control Solenoid / EVAP) and the **Idle Air Control Valve (IACV)** share the same connector style and physical location, they are easily swapped.

* **The IACV Connector** carries a constant +12V power supply, with the ECU switching the ground side via duty cycle to control the valve.

* **The IAT Connector** is a 5V sensor circuit reference from the ECU.

* **The PCS (Purge Control Solenoid) Connector** is also a 12V switched circuit.

If you mistakenly plug the +12V power connector into the IAT sensor (which is a low-resistance thermistor) or swap the IACV and IAT plugs, it routes high current directly into the ECU's low-voltage sensor return/ground driver lanes, instantly frying the transistor at **Q21** and the biasing resistors at **R58** and **R59**.

> [!WARNING]
> **Do not plug in a repaired or new ECU until you have verified your wiring harness connectors!** If the connectors remain swapped, the new components will burn out the moment the ignition is turned on.

---

## Component Identification & Specifications

To fix this issue, you must inspect and replace the following components on the ECU circuit board (typically located near the main harness connectors):

| Component | Board Location | Function | OEM Part / Specification | Common Replacement / Equivalent |
| :--- | :---: | :--- | :--- | :--- |
| **Q21** | Transistor | Low-side ground driver for the IACV solenoid | NEC `01594` (2SD1594) NPN Power Darlington | `2SD1594`, `2SD1998` (D1998), `2SD1020`, or `2SD1415` |
| **R58** | Resistor | Biasing/current-limiting resistor | 1k Ohm, 1/4 W (or 1/2 W) carbon film | 1k Ohm resistor (5% tolerance) |
| **R59** | Resistor | Biasing/current-limiting resistor | 1k Ohm, 1/4 W (or 1/2 W) carbon film | 1k Ohm resistor (5% tolerance) |
| **R61** | Resistor | Driver circuit biasing resistor | 1.2k Ohm, 1/4 W carbon film | 1.2k Ohm resistor (5% tolerance) |

*Note: In JDM surface-mount (SMD) ECUs (e.g. JDM P30, P08), these components may be SMD parts. Ensure you check your board layout version (e.g., `11F0`, `1720`, `1980` board prints).*

---

## Repair Procedure

### Step 1: Verify & Correct the Engine Harness Wiring

Before opening the ECU, trace the wiring plugs on the engine:
1. Check the wire colors at the IACV plug. On USDM harnesses, the IACV plug should have a **Yellow/Black** wire (+12V power) and a **Light Blue** or **Blue/Yellow** wire (ECU Pin A9 control).
2. Check the IAT plug. It typically has a **Red/Yellow** (5V signal) and **Green/White** (Sensor Ground) wire.
3. Replace the IAT sensor if it was subjected to +12V, as it is likely melted or damaged inside.

### Step 2: Extract the ECU and Inspect the Board

1. Remove the ECU from the passenger side kick panel.
2. Remove the top and bottom covers (using a Phillips screwdriver).
3. Search for the **Q21** transistor (mounted to a small heatsink or directly on the board) and resistors **R58** and **R59** nearby.
4. Inspect for black soot, charred resistor bodies, or a cracked casing on the transistor.

### Step 3: Desoldering and Component Replacement

1. Using a high-quality soldering iron and a desoldering pump or wick, gently desolder the legs of the burnt components.
2. Clean the board area with isopropyl alcohol. Check if the copper circuit board traces are lifted or burned. If they are, you will need to jumper them with thin hookup wire.
3. Install the new components (paying attention to the orientation of the Q21 transistor, which must face the same way as the original).
4. Solder and trim the leads.

---

## Related Articles

- [Idle Air Control Valve (IACV) Reference](/cars/sensors/idle-air-control-valve)
- [Intake Air Temperature (IAT) Sensor](/cars/sensors/intake-air-temperature-sensor)
- [Honda ECU Component Sourcing Reference](/cars/ecu/parts-for-ec-us)
- [OBD1 Civic/Integra ECU Families](/cars/diagnostics/obd1-civic-integra-ec-us)
