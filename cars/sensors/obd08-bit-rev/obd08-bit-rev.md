---
summary: '8-bit rev limit and engine speed restart formula for OBD0 VTEC Honda ECUs.'
tags: [ecu, reference, sensors]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD08 Bit Rev'
    url: /pgmfi/wiki/library/obd08-bit-rev
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 8-Bit Rev Limit Formula

For OBD0 Honda VTEC ECUs, the rev limit thresholds and recovery/restart speeds are calculated using the following 8-bit formula:

`RPM = 1848000 / Decimal_Value`

Where:
*   `Decimal_Value` is the base-10 value of the byte at the rev limit address.
