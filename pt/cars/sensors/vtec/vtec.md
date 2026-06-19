---
summary: "VTEC is Honda's variable valve timing system that provides two independent cam profiles for optimized performance across the RPM range."
tags: [vtec, sensors, camshaft, tuning, performance]
applies_to:
  models: [all]
complexity: beginner
---

# VTEC System Overview

VTEC (Variable Valve Timing and Lift Electronic Control) is Honda's proprietary system for variable cam profiles. It effectively provides an engine with two independent camshaft profiles, allowing for optimized performance across different engine speeds.

## Operating Principle

The system utilizes two distinct cam profiles to balance efficiency and power:

*   **Low Cam:** Optimized for low RPM operation, focusing on fuel efficiency, idle stability, and low-end torque.
*   **High Cam:** Optimized for high RPM operation, increasing valve lift and duration to maximize airflow and volumetric efficiency.

> [!NOTE]
> Engines equipped with VTEC typically exhibit a broader power band characterized by two distinct torque curves, as opposed to the single curve found in non-VTEC engines.

## Tuning and Calibration

The **VTEC Crossover Point** is the specific RPM at which the engine switches from the low cam profile to the high cam profile. 

### Determining the Crossover Point
To identify the optimal crossover point for a specific engine configuration:

1.  Perform a dyno pull using only the **Low Cam** profile.
2.  Perform a dyno pull using only the **High Cam** profile.
3.  Overlay the two power graphs.
4.  The intersection point where the High Cam profile begins to produce more power than the Low Cam profile is the ideal crossover point.

{{> vtec-tuning-tips }}
