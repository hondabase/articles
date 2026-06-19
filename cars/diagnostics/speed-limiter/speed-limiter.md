---
summary: 'An overview of how Honda ECU speed limiters function by monitoring the Vehicle Speed Sensor (VSS) and the methods used to bypass them.'
tags: [ecu, sensors, diagnostics, vss]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda ECU Speed Limiter Operation

A speed limiter is a software-based function within the ECU designed to restrict the maximum velocity of the vehicle. In most Honda applications, the ECU monitors the Vehicle Speed Sensor (VSS) and initiates a fuel cut once a pre-programmed speed threshold is exceeded.

## Technical Overview

The speed limiter is a safety and regulatory feature, most commonly found in JDM (Japanese Domestic Market) ECUs, which are typically restricted to 180 km/h.

*   **Input:** The ECU receives a pulsed signal from the VSS.
*   **Logic:** The ECU calculates vehicle speed based on the frequency of the VSS pulses.
*   **Action:** Upon reaching the programmed limit, the ECU disables fuel injection to prevent further acceleration.

> [!NOTE]
> Speed limiting is a function of the ECU's internal programming. Modifying or removing this limit typically requires reflashing the ECU or using an external signal modification device.

## Bypassing the Speed Limiter

There are two primary methods for addressing speed limiters:

1.  **ECU Reprogramming:** Modifying the fuel and ignition maps within the ECU firmware to remove or raise the speed limit threshold. This is the preferred method for performance tuning.
2.  **Signal Modification:** Utilizing a Speed Limit Defencer (SLD) device. These devices intercept the VSS signal before it reaches the ECU, effectively "clipping" or modifying the frequency so the ECU never registers the speed at which the fuel cut is triggered.

> [!WARNING]
> Bypassing factory speed limiters may exceed the mechanical design limits of the vehicle's tires, drivetrain, and suspension. Ensure all vehicle components are rated for the intended top speed before attempting to remove these restrictions.
