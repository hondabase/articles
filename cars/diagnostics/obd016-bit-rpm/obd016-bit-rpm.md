---
summary: 'RPM to 16-bit hex value conversion formula for OBD0 Honda ECUs.'
tags: [ecu, reference, sensors, diagnostics]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD016 Bit RPM'
    url: /pgmfi/wiki/library/obd016-bit-rpm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 16-Bit RPM Formula

To translate engine speed (RPM) to the 16-bit hexadecimal values expected by OBD0 Honda ECUs:

`ECU Hex Value = 1920000 / RPM`

### Excel Conversion

If you are compiling custom ROM tables in Microsoft Excel or Google Sheets, you can calculate the hex string using:

`=DEC2HEX(1920000 / RPM_value)`
