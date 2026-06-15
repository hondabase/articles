---
summary: 'Ignition timing conversion formula for OBD0 Honda ECUs.'
tags: [ecu, reference, sensors]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Ignition'
    url: /pgmfi/wiki/library/obd0-ignition
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Ignition Formula

In OBD0 Honda ECUs, the raw byte value stored in the ROM is converted to ignition advance degrees using the following formula:

`Ignition Advance (Degrees) = (Decimal_Value - 15) * 0.36`

Where:
*   `Decimal_Value` is the base-10 value of the byte located at the ignition map offset (often referred to as the value at the address).
