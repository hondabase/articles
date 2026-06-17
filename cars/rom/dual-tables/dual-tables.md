---
summary: 'Explanation of dual-table ROM structures in Honda ECUs, enabling advanced tuning features like VTEC-dependent fuel and ignition maps.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Dual Tables'
    url: /pgmfi/wiki/library/dual-tables
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Dual Tables

Dual tables simply refers to there being two sets of fuel/timing information in a single [ROM](/cars/rom/rom). [VTEC](/cars/sensors/vtec) is an example of this - there is one set of tuning information for the [Low Cam](/cars/sensors/low-cam) and one for the [High Cam](/cars/sensors/high-cam). Additionally, the [ECUNitrous Control](/cars/rom/ecu-nitrous-control) plans to include two sets of tuning information so that the [ECU](/cars/ecu/ecu) can tune for nitrous. See also: [Dual Roms](/cars/tuning/dual-roms)
