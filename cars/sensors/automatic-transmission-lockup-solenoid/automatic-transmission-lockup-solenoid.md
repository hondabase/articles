---
summary: 'An overview of the Automatic Transmission Lockup Solenoid function, ECU pinout, and common repurposing for OBD0 Honda vehicles.'
tags: [ecu, transmission, sensors, obd0]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# Automatic Transmission Lockup Solenoid

The Automatic Transmission Lockup Solenoid is an electromechanical component located within the automatic transmission assembly. It is responsible for engaging the torque converter lockup mechanism under the direct control of the ECU.

> [!NOTE]
> This solenoid is exclusive to automatic transmission configurations and is not present in manual transmission vehicles.

## ECU Integration
In OBD0 Honda ECU systems, the lockup solenoid is controlled via a dedicated output pin.

| ECU Type | Pin Location | Signal |
| :--- | :--- | :--- |
| OBD0 | A8 | Lockup Solenoid Control |

## Repurposing
Because the lockup solenoid is redundant in manual transmission conversions, the A8 output is frequently repurposed by enthusiasts to control auxiliary devices, such as:

*   VTEC solenoid activation (when converting to a VTEC-capable ECU).
*   Aftermarket shift lights.
*   Data logging triggers.
*   Nitrous oxide system activation.

> [!TIP]
> When repurposing pin A8, ensure the load requirements of the auxiliary device do not exceed the current-sinking capacity of the ECU's internal driver circuit. If the device draws significant current, use the ECU signal to trigger a relay rather than driving the component directly.
