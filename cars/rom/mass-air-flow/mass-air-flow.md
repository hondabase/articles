---
summary: 'A Mass Air Flow (MAF) engine management system utilizes a sensor in the intake tract to directly measure the mass of air entering the engine for precise fuel calculation.'
tags: [ecu, tuning, sensors, airflow, fueling]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Mass Air Flow (MAF) Systems

A Mass Air Flow (MAF) engine management system utilizes a MAF sensor placed within the intake tract to directly measure the mass of air entering the engine. By combining this measurement with known injector flow rates, the [ECU](/cars/ecu/ecu) calculates the precise fuel injector pulse-width required to achieve the target [Air Fuel Ratio](/cars/fueling/air-fuel-ratio).

## Operational Principles

MAF-based systems typically rely on lookup tables that map desired [Air Fuel Ratio](/cars/fueling/air-fuel-ratio) values against measured airflow. 

> [!NOTE]
> This method differs significantly from [Speed Density](/cars/diagnostics/speed-density) systems, such as those found in standard Honda PGM-FI architectures. Speed Density systems utilize [Volumetric Efficiency](/cars/rom/volumetric-efficiency) tables combined with manifold pressure and temperature sensor data to estimate airflow rather than measuring it directly.

## Comparison: MAF vs. Speed Density

| Feature | Mass Air Flow (MAF) | Speed Density |
| :--- | :--- | :--- |
| **Measurement** | Direct mass measurement | Calculated estimation |
| **Primary Inputs** | MAF Sensor | MAP, IAT, TPS, RPM |
| **Complexity** | High sensor sensitivity | High calibration complexity |
| **Honda Application** | Rare (select models) | Standard (PGM-FI) |

## System Components

*   **MAF Sensor:** Measures the mass of air entering the intake.
*   **ECU:** Processes sensor data to determine fuel delivery.
*   **Fuel Injectors:** Deliver fuel based on calculated pulse-width.

> [!TIP]
> When troubleshooting MAF-equipped systems, ensure the sensor housing is free of debris and that the intake tract is sealed, as unmetered air entering after the sensor will cause a lean condition.
