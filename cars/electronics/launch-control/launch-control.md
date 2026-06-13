---
summary: 'Launch control refers to a "twostep" revlimiter. The way this works operationally is fairly simple there is a lower Rev Limiter while the car is stationary,...'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - hardware
  - education
  - tuning
  - rom
  - sensors
  - reference
---

# Launch Control

Launch control refers to a "two-step" revlimiter. The way this works operationally is fairly simple - there is a lower [Rev Limiter](/cars/electronics/rev-limiter) while the car is stationary, so that you can floor it without causing danger to the engine. Pop the clutch, the car starts moving and the low [Rev Limiter](/cars/electronics/rev-limiter) is disabled, allowing you to drive the car normally. The main point of [Launch Control](/cars/electronics/launch-control) is to enable ***consistent*** launches by keeping the car at the same [RPM](/cars/electronics/rpm) each launch.

- [addExtrafeatures.js](addExtrafeatures.js):
