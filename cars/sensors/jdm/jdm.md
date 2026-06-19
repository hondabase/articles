---
summary: 'A technical reference for JDM (Japanese Domestic Market) OBD1 Honda ECUs, highlighting hardware differences and common factory limitations compared to USDM counterparts.'
tags: [ecu, jdm, obd1, sensors, hardware]
applies_to:
  models: [civic, integra]
  chassis: [eg, dc]
complexity: beginner
---

# JDM OBD1 ECU Hardware Reference

Japanese Domestic Market (JDM) ECUs were produced specifically for vehicles sold in the Japanese market. While they share the same fundamental architecture as USDM and EDM units, they feature distinct hardware omissions and factory-programmed limitations.

## Hardware Differences

JDM OBD1 ECUs exhibit several physical and electrical differences compared to their USDM counterparts:

*   **Sensor Omissions:** JDM units typically lack circuitry and support for the Electrical Load Detector (ELD) and the Barometric Pressure (PA) sensor.
*   **Component Density:** JDM boards often utilize a higher concentration of surface-mount components.
*   **Form Factor:** JDM ECUs are housed in a smaller, square-shaped case compared to the rectangular USDM housing.

> [!IMPORTANT]
> Because JDM ECUs lack the internal Barometric Pressure (PA) sensor, they may trigger diagnostic trouble codes or require specific tuning adjustments if swapped into a chassis that expects a PA signal.

## Factory Limitations

JDM ECUs are programmed with specific regional constraints that differ from North American or European specifications:

*   **Speed Limiter:** Most JDM OBD1 ECUs are factory-limited to a top speed of approximately 112 mph (180 km/h).
*   **Fuel/Ignition Maps:** Ignition timing and fuel delivery maps are optimized for the higher-octane fuel standards prevalent in Japan.

## Comparison Summary

| Feature | JDM OBD1 ECU | USDM OBD1 ECU |
| :--- | :--- | :--- |
| **ELD Support** | No | Yes |
| **PA Sensor** | No | Yes |
| **Case Shape** | Square | Rectangular |
| **Speed Limiter** | ~112 mph | Varies (often higher) |

> [!TIP]
> When converting a JDM ECU for use in a USDM vehicle, ensure the wiring harness is modified to account for the missing ELD and PA sensor signals to prevent check engine lights.
