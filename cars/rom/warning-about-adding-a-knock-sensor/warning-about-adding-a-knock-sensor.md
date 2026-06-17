---
summary: 'Technical warning regarding knock sensor installation on non-equipped engines, citing cylinder bore and knock board calibration complexities.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Warning About Adding A Knock Sensor'
    url: /pgmfi/wiki/library/warning-about-adding-a-knock-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Warning About Adding A Knock Sensor

The knock sensor frequency, and thus, its operation, is affected by the bore of the cylinder. From what I can tell, `each` [ECU](/cars/ecu/ecu)'s knock board is also dialed in to specific characteristics of the engine, to filter out engine noise from knock.. using a knock board with an engine other than it was designed for may not be very effective..
