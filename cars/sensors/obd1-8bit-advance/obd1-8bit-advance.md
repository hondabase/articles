---
summary: 'Ignition timing advance conversion formula for 8-bit OBD1 Honda ECUs.'
tags: [ecu, reference, sensors]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit Advance'
    url: /pgmfi/wiki/library/obd1-8bit-advance
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 8-Bit Ignition Advance Formula

In 8-bit OBD1 Honda ECUs, the ignition advance value (in degrees) is calculated from the raw table byte value `v` using the following formula:

`Ignition Advance (Degrees) = (v - 24) / 4`

Where:
* `v` is the decimal representation of the byte at the ignition map cell.
