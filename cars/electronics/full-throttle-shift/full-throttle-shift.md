---
summary: 'Full Throttle ShiftThis is simply an extension of the concept behind FullThrottle Launch (aslo called Launch Control) that allows for a different rev limit...'
applies_to:
  obd: [1]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# Full Throttle Shift

***Full Throttle Shift***This is simply an extension of the concept behind Full-Throttle Launch (aslo called [Launch Control](/cars/electronics/launch-control)) that allows for a different rev limit while the driver is shifting a manual-transission car. Full-throttle shift is usually accomplished hooking the [Rev Limiter](/cars/electronics/rev-limiter) code so that it uses a different rev limit depending on the state of some digital input, namely one hooked to a switch on the clutch... ***Full throttle shift in 3 brain-dead steps:***- First you have to write a routine in assembler to do [Full Throttle Shift](/cars/electronics/full-throttle-shift) (or in hex for you masochists. ;)
- Next you have to make a clutch-mounted switch. For many Hondas without cruise control, the [Cruise Control Switch](/cars/electronics/cruise-control-switch) is probably easiest.
- Connect one side of the switch to ground
- Connect the other side of the switch to the digital input you used in the code (Pin B7 [off(00211h).5 is a nice choice for [OBD1](/cars/electronics/obd1)).

I can almost hear it now... ''"But that's 4 steps Dave ! ! !"'' You're right, I ''DID'' say "3 brain-dead steps"... and the first step ain't one of them :P''
