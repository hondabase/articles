---
summary: 'Boost Cut is a safety mechanism that triggers fuel or spark cut to prevent engine damage caused by excessive manifold pressure.'
tags: [tuning, rom, sensors, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Understanding Boost Cut

Boost Cut is a protective engine management strategy that triggers a **Fuel Cut** or **Spark Cut** when the manifold absolute pressure (MAP) exceeds a pre-defined threshold. This mechanism is designed to prevent catastrophic engine failure caused by over-boost conditions.

## Operational Overview

When the ECU detects that the manifold pressure has surpassed the programmed limit, it immediately intervenes to reduce power output. This is achieved through two primary methods:

*   **Fuel Cut:** The ECU disables the fuel injectors, effectively stopping combustion to prevent lean-condition detonation.
*   **Spark Cut:** The ECU disables the ignition signal, preventing the spark plugs from firing.

> [!IMPORTANT]
> Boost Cut is a safety feature, not a tuning tool. Relying on Boost Cut to regulate boost levels during normal operation can lead to severe engine damage or lean-out conditions.

## Tuning Considerations

In modified applications, the factory Boost Cut threshold is often too low for the desired performance levels. When increasing boost via forced induction, the following steps are required:

1.  **Verify MAP Sensor Range:** Ensure the installed MAP sensor is capable of reading the target boost pressure.
2.  **Adjust Thresholds:** Update the ECU calibration to raise the Boost Cut limit slightly above the target peak boost pressure.
3.  **Validate Safety Margins:** Always maintain a sufficient buffer between the target boost and the Boost Cut threshold to account for atmospheric changes and boost spikes.

> [!WARNING]
> Disabling or setting the Boost Cut threshold excessively high without proper fueling and ignition timing adjustments will remove the engine's primary protection against over-boost, significantly increasing the risk of piston or rod failure.

## Related Diagnostics

If you are experiencing unexpected power loss or engine hesitation under load, check for the following:

*   **MAP Sensor Voltage:** Ensure the sensor is providing a linear signal and is not pegged at the maximum voltage.
*   **Vacuum Leaks:** Leaks in the vacuum lines leading to the MAP sensor can cause erratic pressure readings.
*   **Calibration Errors:** Verify that the ROM settings for the MAP sensor scaling match the hardware installed on the vehicle.

::: widget error-codes :::
