---
summary: 'RPM conversion formula for OBD0 and OBD1 VTEC activation values.'
tags: [ecu, reference, sensors]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0VTEC
    url: /pgmfi/wiki/library/obd0vtec
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 & OBD1 VTEC RPM Formula

In OBD0 and OBD1 Honda VTEC ECUs, the VTEC engagement and disengagement thresholds are determined using the following formula:

`RPM = (Decimal_Value - 128) * 62.52`

Where:

* `Decimal_Value` is the base-10 value of the byte located at the VTEC RPM activation/deactivation addresses in the ROM.
