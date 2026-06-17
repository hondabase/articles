---
summary: 'An overview of Revolutions Per Minute (RPM) as a critical engine parameter for Honda OBD engine management systems.'
tags: [sensors, reference, engine-management]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# Revolutions Per Minute (RPM)

Revolutions Per Minute (RPM) measures the rotational speed of the engine crankshaft, representing the number of full cycles the engine completes in one minute. In Honda engine management systems, the RPM signal is a primary input used to determine fuel injection timing, ignition advance, and VTEC engagement.

## Signal Acquisition
The Engine Control Unit (ECU) calculates RPM by monitoring pulses from the Crankshaft Position (CKP) sensor or the distributor-based sensors (CYP, TDC, and CKP).

> [!IMPORTANT]
> Accurate RPM data is critical for the ECU to maintain stable idle control and correct air-fuel ratios under load. Signal noise or sensor degradation can lead to erratic ignition timing or engine stalling.

## Technical Reference
The following table outlines the standard sensor inputs used by the ECU to derive RPM data across OBD0, OBD1, and OBD2 platforms:

| Sensor | Function | Signal Type |
| :--- | :--- | :--- |
| **CKP** | Crankshaft Position | Pulse |
| **TDC** | Top Dead Center | Pulse |
| **CYP** | Cylinder Position | Pulse |

> [!TIP]
> If experiencing intermittent RPM signal loss, inspect the distributor housing and the wiring harness connectors for corrosion or heat-related insulation failure.

::: widget error-codes :::