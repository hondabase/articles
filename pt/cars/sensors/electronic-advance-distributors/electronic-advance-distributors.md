---
summary: 'An overview of electronic advance distributors, detailing how the ECU manages ignition timing control in Honda OBD0, OBD1, and OBD2 systems.'
tags: [ecu, ignition, sensors, distributors]
complexity: beginner
---

# Electronic Advance Distributors

Electronic advance distributors are ignition systems where the ignition timing advance is dynamically controlled by the ECU rather than relying solely on mechanical centrifugal or vacuum advance mechanisms.

## Overview
In traditional distributor systems, timing advance is determined by mechanical weights and springs (centrifugal) or manifold vacuum levels. Electronic advance distributors replace or augment these mechanical systems, allowing the ECU to calculate optimal ignition timing based on real-time engine load, RPM, and sensor data.

> [!NOTE]
> While the ECU manages the timing curve, the base ignition timing must still be set manually at the distributor housing to ensure the ECU's calculated map aligns with the engine's physical position.

## System Components
The electronic advance system relies on the following components to function:

*   **ECU (Engine Control Unit):** Processes input signals to determine the required ignition advance.
*   **CKP/CYP/TDC Sensors:** Located within the distributor housing, these sensors provide the ECU with precise crankshaft position, cylinder position, and top-dead-center data.
*   **Ignition Control Module (ICM):** Receives the signal from the ECU to trigger the ignition coil at the precise moment calculated by the timing map.

## Operational Logic
The ECU utilizes a 2D or 3D ignition map (lookup table) to determine the advance value. The process follows this sequence:

1.  **Input Acquisition:** The ECU monitors RPM (via CKP) and load (via MAP sensor).
2.  **Map Lookup:** The ECU references the internal ignition map to find the target advance angle for the current operating conditions.
3.  **Signal Output:** The ECU sends a trigger signal to the ICM.
4.  **Spark Delivery:** The ICM interrupts the primary circuit of the ignition coil, inducing a high-voltage spark at the spark plug.

> [!IMPORTANT]
> When troubleshooting ignition timing issues, always verify the base timing with a timing light while the service connector is jumped. This ensures the ECU is in "service mode" and not applying electronic timing corrections during the adjustment process.
