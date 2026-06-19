---
summary: 'A comprehensive guide to diagnosing and repairing the IACV driver circuit on Honda OBD1 ECUs, specifically addressing burnt resistors R58, R59, and the Q21 transistor.'
tags: [ecu, repair, diagnostics, idle, iacv]
applies_to:
  brand: Honda
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eh]
complexity: advanced
---

# OBD1 ECU IACV Circuit Repair: R58, R59, and Q21

A failed Idle Air Control Valve (IACV) driver circuit is a common failure point in Honda OBD1 ECUs, including the P28, P06, P72, P30, and P75. Failure of this circuit prevents the ECU from regulating idle speed, leading to poor engine performance.

## Symptoms of a Burnt IACV Circuit

When the ECU's internal IACV control circuit is damaged, it typically exhibits the following symptoms:

*   **Persistent Check Engine Light (CEL) Code 14:** Indicates an IACV malfunction. The code returns immediately after clearing the ECU, even if the physical valve is replaced.
*   **Extremely Low Idle:** The engine may idle at 200–400 RPM or stall entirely unless the throttle is held open.
*   **Surging or Bouncing Idle:** The idle may oscillate repeatedly between 1000 and 1500 RPM.
*   **Physical ECU Damage:** Visual inspection of the PCB reveals charred, smoked, or cracked resistors at locations **R58** and **R59**, and potentially a failed transistor at **Q21**.

## Root Cause: Swapped Connectors

The most frequent cause of this failure is a wiring error during engine swaps or intake manifold reassembly. The IACV, Intake Air Temperature (IAT) sensor, and Purge Control Solenoid (PCS) connectors share the same physical form factor and are located in close proximity.

*   **IACV Connector:** Carries a constant +12V power supply; the ECU switches the ground side via duty cycle.
*   **IAT Connector:** A 5V sensor circuit reference.
*   **PCS Connector:** A 12V switched circuit.

If the +12V power connector is mistakenly plugged into the IAT sensor, high current is routed into the ECU's low-voltage sensor return/ground driver lanes, instantly destroying the transistor at **Q21** and the biasing resistors at **R58** and **R59**.

> [!WARNING]
> Do not install a repaired or replacement ECU until you have verified your wiring harness connectors. If the connectors remain swapped, the new components will fail immediately upon ignition.

## Component Specifications

Use the following table to identify and source replacement components.

| Component | Board Location | Function | OEM Part / Specification | Common Replacement |
| :--- | :---: | :--- | :--- | :--- |
| **Q21** | Transistor | Low-side ground driver | NEC 01594 (2SD1594) | 2SD1594, 2SD1998, 2SD1020, 2SD1415 |
| **R58** | Resistor | Biasing/current-limiting | 1k Ohm, 1/4 W carbon film | 1k Ohm (5% tolerance) |
| **R59** | Resistor | Biasing/current-limiting | 1k Ohm, 1/4 W carbon film | 1k Ohm (5% tolerance) |
| **R61** | Resistor | Driver circuit biasing | 1.2k Ohm, 1/4 W carbon film | 1.2k Ohm (5% tolerance) |

> [!NOTE]
> In JDM surface-mount (SMD) ECUs (e.g., JDM P30, P08), these components may be SMD parts. Verify your specific board revision (e.g., 11F0, 1720, 1980) before sourcing parts.

## Repair Procedure

### 1. Verify Engine Harness Wiring
Before servicing the ECU, inspect the engine harness:
*   **IACV Plug:** Verify the presence of a Yellow/Black wire (+12V) and a Light Blue or Blue/Yellow wire (ECU Pin A9).
*   **IAT Plug:** Verify the presence of a Red/Yellow (5V signal) and Green/White (Sensor Ground) wire.
*   **Sensor Health:** Replace the IAT sensor if it was subjected to +12V, as the internal thermistor is likely damaged.

### 2. ECU Inspection
1. Remove the ECU from the vehicle.
2. Remove the top and bottom covers.
3. Locate **Q21** (mounted to a heatsink or the PCB) and resistors **R58** and **R59**.
4. Inspect for signs of thermal damage, such as soot, charred bodies, or cracked casings.

### 3. Component Replacement
1. Use a high-quality soldering iron and desoldering pump or wick to remove the damaged components.
2. Clean the PCB area with isopropyl alcohol. 
3. Inspect copper traces for lifting or burning. If traces are damaged, perform a jumper repair using thin-gauge hookup wire.
4. Install new components, ensuring the **Q21** transistor is oriented identically to the original.
5. Solder the leads and trim excess length.

## Related Resources
*   {{> iacv-troubleshooting }}
*   {{> ecu-component-sourcing }}
*   ::: widget error-codes :::
