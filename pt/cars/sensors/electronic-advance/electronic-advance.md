---
summary: 'An overview of Electronic Advance systems, where ignition timing is dynamically controlled by the ECU to replace traditional vacuum-based mechanical systems.'
tags: [ecu, ignition, tuning, sensors]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# Electronic Ignition Advance

Electronic Advance refers to an engine configuration where ignition timing is dynamically controlled by the ECU. This system replaced traditional vacuum advance mechanisms, providing significantly greater flexibility for engine tuning and precise ignition control.

## Overview
Unlike mechanical vacuum advance, which relies on manifold pressure to physically adjust timing, Electronic Advance allows the ECU to calculate the optimal ignition timing based on real-time sensor data. This enables:

*   **Precise Timing Maps:** Ignition timing can be mapped against load, RPM, and temperature.
*   **Improved Efficiency:** Optimized combustion cycles across the entire operating range.
*   **Enhanced Tuning Capability:** Easier adjustments for modified engines compared to mechanical spring/weight systems.

> [!NOTE]
> While Electronic Advance was a major advancement over mechanical systems, modern engine management has largely transitioned to distributorless direct-fire ignition systems for even greater control and reliability.

## System Components
The ECU determines the ignition timing by processing inputs from several key sensors:

*   **Crankshaft Position Sensor (CKP):** Provides engine speed and piston position data.
*   **Manifold Absolute Pressure (MAP):** Measures engine load.
*   **Coolant Temperature Sensor (ECT):** Adjusts timing based on engine thermal state.
*   **Throttle Position Sensor (TPS):** Monitors driver demand and rate of change.

{{> ignition-timing-basics }}