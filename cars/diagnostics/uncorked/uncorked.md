---
summary: 'The stock code divides the Map Sensor reading by two. This caps the maximum pressure the ECU can respond to by half the maximum of what the Map Sensor is capable of reading.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: uncorked
    url: /pgmfi/wiki/library/uncorked
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# uncorked

The stock code divides the [Map Sensor](/cars/fueling/map-sensor) reading by two. This caps the maximum pressure the [ECU](/cars/ecu/ecu) can respond to by half the maximum of what the [Map Sensor](/cars/fueling/map-sensor) is capable of reading. By simply removing this division, we have uncorked the [Map Sensor](/cars/fueling/map-sensor) to read all the way up to 11psi of boost.
