---
summary: 'Closed-loop fuel control basics for Honda tuning, including open-loop fallback, wideband and narrowband targets, fuel trim limits, and activation rules.'
tags: [fuel, tuning, wideband, lambda, sensors]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: Hondata Help
    title: Closed Loop Parameters
    url: https://www.hondata.com/help/smanager/closedloopparameters.htm
    license: 'All rights reserved'
    license_url: https://www.hondata.com/
    retrieved_at: '2026-06-19'
    used_for: reference
---

# Closed-Loop Fuel Control

Closed-loop fuel control lets the ECU use oxygen sensor feedback to trim fueling toward a target mixture. In practice, that means the ECU can correct the calibration after warmup, during light-load operation, and in the conditions where emissions and fuel economy matter most.

## Operating Modes

The Hondata-style closed-loop setup typically gives you four practical modes:

| Mode | Behavior |
| :--- | :--- |
| **Open loop** | Closed-loop corrections are disabled |
| **Stock sensor** | Uses the factory narrowband oxygen sensor |
| **Wideband voltage target** | Uses a wideband input with a fixed voltage target |
| **Wideband lambda target** | Uses a wideband input with a dynamic lambda target |

> [!NOTE]
> While you are tuning fuel and ignition maps, closed loop is often best disabled. Otherwise the ECU can trim away the changes you are trying to measure.

## The Control Limits

Closed-loop operation is usually constrained by a small set of thresholds:

* Maximum MAP for closed loop
* Maximum engine speed
* Delay after engine start
* Inactivity timeout
* TPS threshold for switching between closed loop and open loop

Those limits decide when the ECU is allowed to trim, and when it should leave fuel alone.

## Fuel Trims

Short-term and long-term fuel trims are there to keep the mixture near the target without constantly rewriting the base map.

* Long-term trim sets the slow correction band.
* Short-term trim sets the fast correction band.
* Rate-of-change settings decide how quickly the ECU moves the short-term trim in rich-to-lean and lean-to-rich directions.

> [!IMPORTANT]
> If the short-term fuel trim is swinging too far or too slowly, fix the trim rate and thresholds before assuming the base fuel map is wrong.

## Practical Setup

1. Use open loop while building the base fuel table.
2. Set narrowband or wideband mode according to the sensor you actually have installed.
3. Disable the O2 heater if the stock sensor is absent.
4. Keep the closed-loop MAP and TPS thresholds conservative enough that the ECU leaves open loop under load.
5. Verify that the trim ranges are wide enough to correct small errors, but not so wide that they hide a bad calibration.

## What Good Behavior Looks Like

In a stable closed-loop setup, the ECU should move around the target without large oscillations. If the sensor, ground, or calibration is unstable, the trims tend to chase the signal instead of refining it.

> [!TIP]
> A healthy closed-loop setup usually shows small, repeated corrections during cruise rather than large delayed swings. That is the sign the ECU is trimming around the target instead of fighting it.
