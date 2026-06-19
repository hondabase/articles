---
summary: 'Technical reference for converting engine speed (RPM) to 16-bit hexadecimal values for OBD0 Honda ECU tuning and ROM modification.'
tags: [ecu, tuning, obd0, diagnostics, rom]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 16-Bit RPM Conversion Formula

To translate engine speed (RPM) into the 16-bit hexadecimal values required for OBD0 Honda ECU ROM tables, use the following calculation:

`ECU Hex Value = 1920000 / RPM`

> [!IMPORTANT]
> The resulting value must be converted to hexadecimal format for entry into ECU mapping software or binary editors.

### Spreadsheet Implementation

When working with custom ROM tables in Microsoft Excel or Google Sheets, use the following formula to automatically calculate the required hex string:

`=DEC2HEX(1920000 / [Cell_Reference])`

### Reference Table

| RPM | Calculation | Hex Value |
| :--- | :--- | :--- |
| 1000 | 1920000 / 1000 | 0768 |
| 3000 | 1920000 / 3000 | 0280 |
| 5000 | 1920000 / 5000 | 0180 |
| 7000 | 1920000 / 7000 | 0113 |
| 9000 | 1920000 / 9000 | 00D5 |
