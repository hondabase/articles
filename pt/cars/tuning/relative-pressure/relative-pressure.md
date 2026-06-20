---
summary: 'Relative pressure describes gauge pressure measurements that exclude atmospheric pressure (~14.5 psi). Understanding the distinction between relative and absolute pressure is essential for tuning and sensor interpretation.'
tags: [tuning, sensors, reference, relative-pressure, absolute-pressure, map-sensor]
complexity: intermediate
---

# Relative Pressure

## Overview

Relative pressure (gauge pressure) is measured with atmospheric pressure as the reference point rather than absolute vacuum. Since we exist under constant atmospheric pressure (approximately 14.5 psi), a gauge reading of 10 psi relative pressure actually represents 24.5 psi of absolute pressure (10 + 14.5).

> [!IMPORTANT]
> Relative pressure = Gauge pressure. Absolute pressure = Gauge pressure + Atmospheric pressure (~14.5 psi).

## Relative Pressure Tables in ROM Editors

ROM editors displaying relative pressure tables present atmospheric conditions as the baseline reference. The following characteristics are typical:

- **Column 10 (Atmospheric Baseline):** Approximately atmospheric pressure; may read slightly lower due to interpolation or residual vacuum during wide-open throttle (WOT) conditions.
- **Column 1 (Arbitrary Reference):** Not true zero (absolute vacuum); an arbitrary scaling reference specific to sensor and ECU implementation.

![rel_pressure_uber.jpg](rel_pressure_uber.jpg)
*Example: Relative pressure table in ROM editor showing atmospheric and WOT conditions*

## Related Components

- **MAP Sensor:** Reference the [MAP sensor documentation](/cars/fueling/map-sensor) for OEM sensor range specifications and original calibration values.
- **Wide-Open Throttle (WOT):** Under WOT conditions, some residual manifold vacuum typically remains; this is reflected in relative pressure readings rather than absolute zero.
