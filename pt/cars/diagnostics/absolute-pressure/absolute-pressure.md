---
summary: 'Understanding Absolute Pressure (MAP) measurements, including the relationship between atmospheric pressure, boost, and vacuum scales.'
tags: [tuning, rom, sensors, diagnostics, ecu]
complexity: intermediate
---

# Understanding Absolute Pressure

Absolute Pressure refers to pressure measurements taken on a scale where [Absolute Vacuum](/cars/sensors/absolute-vacuum) equals 0.

*   **Atmospheric Pressure:** Approximately 14.7 psi at sea level when measured as absolute pressure.
*   **Boost Pressure:** 10 psi of boost is approximately 24.7 psi absolute (14.7 psi atmospheric + 10 psi boost).
*   **Tire Pressure:** 30 psi of tire pressure is approximately 44.7 psi absolute (14.7 psi atmospheric + 30 psi tire pressure).

## ECU Mapping and Absolute Pressure

When tuning, ECU editors typically display values in Absolute Pressure.

> [!NOTE]
> Column 10 in standard mapping software typically represents atmospheric pressure. Values may appear slightly lower due to interpolation or minor vacuum present even at Wide Open Throttle (WOT).

Column 1 is arbitrary and does not represent true zero (absolute vacuum). 

### Reference Data
For specific operating ranges and voltage scaling, refer to the [MAP Sensor](/cars/fueling/map-sensor) documentation to determine the maximum pressure limits of OEM sensors.

![Absolute Pressure mapping in tuning software](abs_pressure_crome.jpg)
*Example of absolute pressure scaling in ECU tuning software*
