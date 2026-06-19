---
summary: 'An overview of absolute pressure measurement in automotive tuning, explaining the relationship between atmospheric pressure, boost, and vacuum.'
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Understanding Absolute Pressure in ECU Tuning

Absolute pressure is a measurement scale where absolute vacuum is defined as 0. In automotive engine management, this scale is critical for calculating air density and fuel requirements.

## Pressure Definitions
*   **Atmospheric Pressure:** Approximately 14.7 psi at sea level.
*   **Boost Pressure:** Measured as gauge pressure. To calculate absolute pressure, add atmospheric pressure to the boost value (e.g., 10 psi of boost + 14.7 psi atmospheric = 24.7 psi absolute).
*   **Tire Pressure:** Similarly, a tire gauge reading of 30 psi represents approximately 44.7 psi absolute pressure.

> [!NOTE]
> Absolute pressure calculations must account for altitude, as atmospheric pressure decreases as elevation increases.

## ECU Mapping and Absolute Pressure
Tuning software often utilizes absolute pressure scales for fuel and ignition tables. 

![Crome tuning software interface showing absolute pressure columns](abs_pressure_crome.jpg)

*   **Atmospheric Columns:** In the example above, column 10 represents atmospheric pressure. Values may appear slightly lower than 14.7 psi due to interpolation or minor pressure drops at wide-open throttle (WOT).
*   **Vacuum Columns:** Column 1 represents a vacuum state, though it is rarely calibrated to absolute zero.

## Related Components
For further information on how the ECU interprets these pressure values, refer to the following:

*   **[MAP Sensor](/cars/fueling/map-sensor):** Review the operational limits and voltage scaling of the OEM manifold absolute pressure sensor.
*   **[Atmospheric Pressure Sensor](/cars/wiring/atmospheric-pressure):** Details on the barometric pressure sensor used for altitude compensation.
