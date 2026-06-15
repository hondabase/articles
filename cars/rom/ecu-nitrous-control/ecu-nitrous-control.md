---
summary: 'ppl are working on a ROM where the ECU activates the nitrous solenoid instead of the usual WOT switch.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'ECU Nitrous Control'
    url: /pgmfi/wiki/library/ecu-nitrous-control
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ECU Nitrous Control

ppl are working on a [ROM](/cars/rom/rom) where the [ECU](/cars/ecu/ecu) activates the nitrous solenoid instead of the usual [WOT](/cars/reference/wot) switch. The main advantage of this is that the [ECU](/cars/ecu/ecu) knows when nitrous is active, and can therefore switch to a different set of fuel/timing maps. Dry kit + 450cc injectors + [ECUNitrous Control](/cars/rom/ecu-nitrous-control) w/ [Dual Tables](/cars/rom/dual-tables) = FINE TUNED wet kit!
