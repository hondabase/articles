---
summary: 'An overview of Exhaust Gas Temperature (EGT) sensors and their role in monitoring ignition timing and engine health during the tuning process.'
tags: [sensor, tuning, diagnostics, egt]
applies_to:
  models: [civic, crx, del-sol, integra, prelude, accord, s2000, nsx]
  chassis: [ef, eg, ek, da, dc2, bb, cb-cd, ap1, ap2, na1-na2]
complexity: intermediate
---

# Exhaust Gas Temperature (EGT) Sensor Overview

The Exhaust Gas Temperature (EGT) sensor is an external monitoring device installed in the exhaust manifold or header, positioned as close to the cylinder head as possible. When used in conjunction with a wideband oxygen sensor and data logging, it serves as a critical diagnostic tool for ECU calibration.

## Tuning Applications
While the wideband O2 sensor is the primary tool for monitoring Air/Fuel Ratio (AFR), the EGT sensor provides essential data regarding combustion efficiency and ignition timing.

> [!NOTE]
> EGT readings are highly dependent on sensor placement. Consistent placement across all cylinders or at the collector is required for accurate comparative analysis.

### Ignition Timing Analysis
Assuming the engine is operating at a target AFR, EGT values provide insight into the accuracy of the ignition timing:

*   **Retarded Timing:** Generally results in higher EGTs, as combustion continues further into the exhaust stroke, transferring more heat to the exhaust gases.
*   **Advanced Timing:** Generally results in lower EGTs, as more heat energy is converted into cylinder pressure during the power stroke.

> [!WARNING]
> EGTs should not be used as a primary tool for determining AFR. Always prioritize wideband O2 data for fuel mixture adjustments to prevent engine damage.

## Installation Considerations
For optimal performance and longevity, adhere to the following guidelines:

*   **Proximity:** Install the probe as close to the exhaust port as possible to minimize heat loss and latency.
*   **Depth:** Ensure the probe tip is positioned in the center of the exhaust stream to capture an accurate average temperature.
*   **Data Logging:** Integrate the EGT signal into your ECU data logging system to correlate temperature spikes with specific RPM and load points.
