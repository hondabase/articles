---
summary: 'An overview of the Revolutions Per Minute (RPM) signal, its role in engine management, and its function as a primary reference for Honda ECU operation.'
tags: [sensors, reference, ignition, timing]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Revolutions Per Minute (RPM) Signal

Revolutions Per Minute (RPM) represents the rotational speed of the engine crankshaft, measured in cycles per minute. In Honda engine management systems, the RPM signal is the primary reference used by the ECU to determine fuel injection timing, ignition advance, and idle control strategies.

## Signal Generation
The ECU derives the RPM signal from the Crankshaft Position (CKP) sensor, Top Dead Center (TDC) sensor, and Cylinder Position (CYP) sensor located within the distributor or on the crankshaft.

*   **CKP Sensor:** Provides the high-resolution signal used to calculate instantaneous engine speed.
*   **TDC Sensor:** Identifies the piston position for cylinder #1 to synchronize ignition and injection events.
*   **CYP Sensor:** Distinguishes between individual cylinders to allow for sequential fuel injection.

## ECU Processing
The ECU processes these pulse signals to calculate the engine's current operating state. This data is mapped against internal lookup tables to determine:

*   **Fuel Injection Duration:** Adjusting pulse width based on load and speed.
*   **Ignition Timing:** Advancing or retarding spark based on the RPM-to-load ratio.
*   **VTEC Engagement:** Monitoring RPM thresholds to trigger the VTEC solenoid.
*   **Idle Air Control:** Adjusting the IACV duty cycle to maintain a target idle speed.

> [!NOTE]
> Signal interference or a failing sensor will typically trigger a Diagnostic Trouble Code (DTC) related to the ignition system or crankshaft position, often resulting in a "limp mode" or a no-start condition.

## Technical Specifications
The following table outlines the standard sensor roles in RPM calculation:

| Sensor | Function | Signal Type |
| :--- | :--- | :--- |
| **CKP** | Crankshaft Position | Variable Reluctance / Hall Effect |
| **TDC** | Top Dead Center | Variable Reluctance / Hall Effect |
| **CYP** | Cylinder Position | Variable Reluctance / Hall Effect |

{{> sensor-troubleshooting-guide }}