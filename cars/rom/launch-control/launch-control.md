---
summary: 'Launch control refers to a "twostep" revlimiter. The way this works operationally is fairly simple there is a lower Rev Limiter while the car is stationary,...'
tags: [hardware, education, tuning, rom, sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Launch Control'
    url: /pgmfi/wiki/library/launch-control
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Launch Control

Launch control refers to a "two-step" revlimiter. The way this works operationally is fairly simple - there is a lower [Rev Limiter](/cars/sensors/rev-limiter) while the car is stationary, so that you can floor it without causing danger to the engine. Pop the clutch, the car starts moving and the low [Rev Limiter](/cars/sensors/rev-limiter) is disabled, allowing you to drive the car normally. The main point of [Launch Control](/cars/rom/launch-control) is to enable ***consistent*** launches by keeping the car at the same [RPM](/cars/sensors/rpm) `each` launch.

- [addExtrafeatures.js](addExtrafeatures.js):
