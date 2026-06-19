---
summary: 'Volumetric Efficiency (VE) defines the ratio of air/fuel mixture drawn into the cylinder versus its theoretical maximum capacity, serving as the foundation for ECU fuel mapping.'
tags: [ecu, tuning, rom, sensors, fueling]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Volumetric Efficiency (VE)

Volumetric Efficiency (VE), also referred to as "Pumping Efficiency," is the ratio of the actual volume of air/fuel mixture drawn into the cylinder compared to the theoretical volume of the cylinder.

*   **Naturally Aspirated Engines:** Typically achieve approximately 80% VE.
*   **Forced Induction Engines:** Frequently exceed 100% VE due to pressurized intake charges.

## ECU Fuel Mapping
Fuel tables within Honda ECUs function as volumetric efficiency tables. The ECU calculates the required fuel delivery by utilizing the VE value alongside the theoretical maximum airflow and injector scaling.

The fundamental calculation is represented as:
**Injector Size × VE × Theoretical Pumping Possibility**

> [!NOTE]
> This calculation assumes standard temperature and atmospheric pressure conditions based on the [Ideal Gas Law](/cars/rom/ideal-gas-law). This approach optimizes ECU processing by pre-calculating airflow requirements rather than performing real-time Ideal Gas Law computations.

## Environmental Corrections
Because the VE table is mapped to specific assumed conditions, the ECU utilizes sensor data to adjust for real-world variables:

*   **Intake Air Temperature (IAT):** The [Intake Air Temperature Sensor](/cars/sensors/intake-air-temperature-sensor) provides data to correct the fueling based on the actual density of the intake charge compared to the baseline values used in the VE table.
*   **Atmospheric Pressure:** Variations in barometric pressure are accounted for to maintain the target [Air Fuel Ratio](/cars/fueling/air-fuel-ratio) across varying altitudes.
