---
summary: 'Technical explanation of launch control "two-step" rev limiter features in Honda ECUs, enabling consistent standing starts by utilizing a secondary RPM limit.'
tags: [tuning, rom, sensors, launch-control, ecu]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda ECU Launch Control (Two-Step) Implementation

Launch control, commonly referred to as a "two-step" rev limiter, provides a secondary, lower RPM limit while the vehicle is stationary. This allows the driver to maintain a consistent engine speed for standing starts without risking engine damage or excessive wheel spin.

## Operational Overview

The system functions by monitoring vehicle speed and engine RPM. When the ECU detects that the vehicle is stationary, it engages the secondary rev limiter. Once the clutch is released and the vehicle begins to move, the ECU disables the lower limit, allowing the engine to reach the standard operating RPM range.

> [!NOTE]
> The primary objective of launch control is to ensure repeatable launch performance by maintaining a consistent RPM setpoint across multiple runs.

## Technical Requirements

To implement launch control, the ECU must be capable of processing vehicle speed sensor (VSS) data and executing modified code within the ROM. 

### Implementation Components

*   **VSS Signal:** Required to determine if the vehicle is stationary.
*   **RPM Signal:** Required to trigger the fuel or ignition cut once the threshold is reached.
*   **Modified ROM:** The ECU firmware must be patched to include the secondary limiter logic.

> [!TIP]
> Ensure the VSS is functioning correctly before enabling launch control. If the ECU does not receive a valid speed signal, the launch limiter may remain active while the vehicle is in motion.

## Configuration

The following script is used to inject the necessary logic into the ECU firmware:

- `addExtrafeatures.js`: This script modifies the ROM to enable the two-step functionality and allows for the adjustment of the launch RPM threshold.
