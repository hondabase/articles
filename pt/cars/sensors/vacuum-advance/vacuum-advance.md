---
summary: 'Vacuum advance is a mechanical method for varying spark advance based on engine load, independent of ECU control.'
tags: [ecu, ignition, tuning, sensors]
complexity: beginner
---

# Vacuum Advance Mechanics

Vacuum advance is a purely mechanical method used to vary the amount of [Spark Advance](/cars/sensors/spark-advance) based on engine load.

## Operation
A distributor equipped with a vacuum advance unit is connected to a manifold vacuum source. As engine vacuum increases (typically during light load or deceleration), the suction force rotates the distributor plate, which physically advances the ignition timing.

> [!IMPORTANT]
> The [ECU](/cars/ecu/ecu) cannot control or modify ignition timing on engines equipped with a mechanical vacuum advance distributor. 

## Limitations
Because the system relies entirely on manifold pressure, it lacks the precision and multi-dimensional mapping capabilities of electronic ignition systems. 

* **Load Sensitivity:** Timing is adjusted solely based on vacuum levels, ignoring factors like intake air temperature or coolant temperature.
* **ECU Incompatibility:** Electronic ignition control systems require a fixed distributor or a crank-triggered system to function; vacuum advance units are incompatible with these setups.

{{> ignition-timing-basics }}
