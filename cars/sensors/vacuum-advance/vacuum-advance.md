---
summary: 'Vacuum advance is a mechanical system that adjusts ignition timing based on engine load, operating independently of the ECU.'
tags: [ecu, ignition, sensors, timing]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Vacuum Advance Ignition Systems

Vacuum advance is a mechanical method for varying the amount of [Spark Advance](/cars/sensors/spark-advance) based on engine load. 

## Operating Principle
A vacuum-advance distributor is connected directly to a source of engine vacuum. As engine vacuum increases (typically during light-load or cruising conditions), the resulting suction acts upon a diaphragm within the distributor. This force rotates the distributor plate, which physically advances the ignition timing.

> [!IMPORTANT]
> The [ECU](/cars/ecu/ecu) cannot control or modify ignition timing on a vehicle equipped with a vacuum-advance distributor. These systems operate entirely independently of electronic engine management.

## System Limitations
* **Mechanical Dependency:** Timing adjustments are dictated solely by manifold or ported vacuum levels, rather than calculated engine load maps.
* **Lack of ECU Integration:** Because the system is purely mechanical, it cannot compensate for variables such as intake air temperature, coolant temperature, or knock detection.
* **Tuning Constraints:** Ignition curves cannot be remapped or adjusted via software; changes to the timing curve require physical modification of the distributor springs or vacuum canister.
