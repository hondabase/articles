---
summary: 'Electronic Advance Distributors allow the ECU to dynamically control spark advance timing for optimized engine performance.'
tags: [ecu, ignition, sensors, distributors]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Electronic Advance Distributors

Electronic Advance Distributors are ignition systems that allow the engine control unit (ECU) to dynamically adjust spark advance timing. Unlike traditional mechanical distributors that rely solely on vacuum or centrifugal weights, these units utilize electronic signals to optimize ignition timing based on real-time engine load and RPM.

## System Overview

The distributor functions as both a high-voltage distribution point for the spark plugs and a sensor array for the ECU. By manipulating the ignition signal, the ECU can advance or retard timing to prevent detonation, improve fuel efficiency, and maximize power output.

> [!NOTE]
> Electronic Advance Distributors are distinct from mechanical advance units found in older carbureted engines. Ensure the ECU being used is compatible with the specific distributor's internal sensor configuration (e.g., CKP, CYP, and TDC sensors).

## Key Components

*   **Ignition Control Module (ICM):** The internal component responsible for switching the primary ignition coil circuit on and off based on the ECU's trigger signal.
*   **Internal Sensors:** Most Honda Electronic Advance Distributors contain three sensors:
    *   **CKP (Crankshaft Position):** Monitors engine RPM.
    *   **TDC (Top Dead Center):** Identifies the position of the number one cylinder.
    *   **CYP (Cylinder Position):** Identifies the specific cylinder for sequential fuel injection.

## Troubleshooting and Diagnostics

If the engine fails to start or exhibits erratic timing, verify the integrity of the distributor internal sensors and the wiring harness.

> [!CAUTION]
> Do not attempt to bypass the ICM or modify the internal sensor wiring without a proper wiring diagram, as this can cause permanent damage to the ECU's ignition driver circuit.

### Common Diagnostic Steps
1.  **Check for Spark:** Use an inline spark tester to confirm high-voltage output from the coil.
2.  **Verify Sensor Signals:** Use an oscilloscope to check for clean square-wave signals from the CKP, TDC, and CYP sensors while cranking.
3.  **Inspect Grounding:** Ensure the distributor housing is properly grounded to the cylinder head, as poor grounding can lead to signal noise and misfires.

{{> ignition-system-maintenance }}
