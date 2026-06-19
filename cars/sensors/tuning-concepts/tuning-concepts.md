---
summary: 'A comprehensive reference guide to essential engine tuning concepts, including sensor data, air-fuel ratios, and diagnostic logging.'
tags: [tuning, sensors, fueling, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Engine Tuning Concepts and Reference

This guide provides an overview of fundamental tuning concepts required for engine management and performance calibration.

## Sensor and Fueling Fundamentals

Understanding the relationship between sensor data and combustion efficiency is critical for effective tuning.

*   **Air Fuel Ratio (AFR):** The mass ratio of air to fuel present in the combustion chamber. Maintaining the correct AFR is essential for engine longevity and power output.
*   **Wideband O2:** Unlike narrow-band sensors, wideband oxygen sensors provide precise AFR readings across a broad range, allowing for accurate closed-loop fuel control.
*   **Exhaust Gas Temp (EGT) Sensor:** Monitors the temperature of exhaust gases. High EGTs can indicate lean conditions or excessive ignition timing, serving as a vital safety metric for high-performance engines.
*   **Injector Sizing:** The process of selecting fuel injectors with the appropriate flow rate to meet the engine's power goals while maintaining a safe duty cycle.

## Diagnostics and Calibration

Modern engine management relies on the ability to capture and interpret real-time data.

*   **Data Logging:** The recording of sensor inputs and ECU outputs over time. This data is used to identify performance bottlenecks, knock events, and tuning inconsistencies.
*   **Real-Time Programmability:** The capability to adjust ECU parameters (such as fuel maps and ignition timing) while the engine is running, allowing for immediate feedback and optimization.

> [!TIP]
> Use the wideband wiring reference tool to ensure your sensor is correctly integrated into your ECU harness.

::: widget wideband-wiring-table :::

## Related Documentation

For further technical details on specific components, refer to the following sections:

*   [Exhaust Gas Temp Sensor](/cars/tuning/exhaust-gas-temp-sensor)
*   [Wide Band O2](/cars/fueling/wide-band-o2)
*   [Data Logging](/cars/diagnostics/data-logging)
*   [Real Time Programability](/cars/diagnostics/real-time-programability)
*   [Air Fuel Ratio](/cars/fueling/air-fuel-ratio)
*   [Injector Sizing](/cars/fueling/injector-sizing)
