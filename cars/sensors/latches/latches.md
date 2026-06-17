---
summary: 'Technical explanation of address latches (e.g., 74HC373) used in Honda OBD1 ECUs to interface the MCU with external EPROM memory.'
tags: [sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: latches
    url: /pgmfi/wiki/library/latches
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# latches

A logic gate that preserves the state of [IO](/cars/sensors/io) lines
