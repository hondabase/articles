---
summary: 'A guide to implementing Full Throttle Shift (FTS) in Honda OBD1 ECUs, allowing for faster gear changes by maintaining boost and RPM during shifts.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  brand: Honda
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Full Throttle Shift'
    url: /pgmfi/wiki/library/full-throttle-shift
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Full Throttle Shift

***Full Throttle Shift***This is simply an extension of the concept behind Full-Throttle Launch (aslo called [Launch Control](/cars/rom/launch-control)) that allows for a different rev limit while the driver is shifting a manual-transission car. Full-throttle shift is usually accomplished hooking the [Rev Limiter](/cars/sensors/rev-limiter) code so that it uses a different rev limit depending on the state of some digital input, namely one hooked to a switch on the clutch... ***Full throttle shift in 3 brain-dead steps:***- First you have to write a routine in assembler to do [Full Throttle Shift](/cars/diagnostics/full-throttle-shift) (or in hex for you masochists. ;)
- Next you have to make a clutch-mounted switch. For many Hondas without cruise control, the [Cruise Control Switch](/cars/wiring/cruise-control-switch) is probably easiest.
- Connect one side of the switch to ground
- Connect the other side of the switch to the digital input you used in the code (Pin B7 [off(00211h).5 is a nice choice for [OBD1](/cars/wiring/obd1)).

I can almost hear it now... ''"But that's 4 steps Dave ! ! !"'' You're right, I ''DID'' say "3 brain-dead steps"... and the first step ain't one of them :P''
