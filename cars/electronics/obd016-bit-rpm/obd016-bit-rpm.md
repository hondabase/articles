---
summary: 'RPM to 16-bit hex value conversion formula for OBD0 Honda ECUs.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - diagnostics
---

# OBD0 16-Bit RPM Formula

To translate engine speed (RPM) to the 16-bit hexadecimal values expected by OBD0 Honda ECUs:

`ECU Hex Value = 1920000 / RPM`

### Excel Conversion
If you are compiling custom ROM tables in Microsoft Excel or Google Sheets, you can calculate the hex string using:

`=DEC2HEX(1920000 / RPM_value)`
