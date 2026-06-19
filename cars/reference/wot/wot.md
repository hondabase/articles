---
summary: 'Definition and technical significance of Wide Open Throttle (WOT) in Honda engine management, fuel mapping, and diagnostic procedures.'
tags: [tuning, diagnostics, fuel-mapping, sensors]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Wide Open Throttle (WOT) Definition and Tuning Significance

Wide Open Throttle (WOT) refers to the condition where the engine's throttle plate is fully open, allowing maximum airflow into the intake manifold. In Honda engine management systems, this state triggers specific fuel and ignition maps designed to prioritize power output over fuel economy.

## Technical Significance
When the ECU detects a WOT condition—typically determined by the Throttle Position Sensor (TPS) voltage exceeding a calibrated threshold—it transitions from "Closed Loop" to "Open Loop" operation.

> [!IMPORTANT]
> During WOT, the ECU ignores input from the Narrowband Oxygen (O2) sensor. The engine relies exclusively on pre-programmed fuel and ignition tables (lookup tables) to determine the air-fuel ratio (AFR) and timing advance.

## Diagnostic and Tuning Considerations
Proper identification of the WOT threshold is critical for accurate engine calibration. If the TPS is miscalibrated, the ECU may fail to enter the WOT fuel map, resulting in a lean condition or suboptimal power delivery.

### Common WOT Tuning Parameters
*   **TPS Threshold:** The voltage at which the ECU switches to the WOT map.
*   **Fuel Enrichment:** Additional fuel injected to prevent detonation and cool the combustion chamber under high load.
*   **Ignition Advance:** Timing maps optimized for maximum brake torque (MBT) at high load/high RPM.

> [!TIP]
> Always verify that your TPS reads 0% at idle and 100% at full pedal depression using your tuning software or a multimeter before adjusting WOT fuel tables.

## Related References
{{> resistor-color-codes }}

::: widget wideband-wiring-table :::
