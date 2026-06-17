---
summary: 'Technical reference for calculating 8-bit rev limit and engine speed restart thresholds in OBD0 VTEC Honda ECUs.'
tags: [ecu, tuning, obd0, vtec, formula]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: intermediate
---

# OBD0 8-Bit Rev Limit and Restart Formula

OBD0 VTEC ECUs utilize an 8-bit memory structure to define engine speed thresholds. The rev limit and the associated engine speed restart (recovery) values are calculated using a fixed constant.

## Calculation Formula

The engine speed in RPM is determined by the following formula:

`RPM = 1,848,000 / Decimal_Value`

**Where:**
* **Decimal_Value:** The base-10 integer representation of the hex byte stored at the specific memory address.

> [!IMPORTANT]
> The `Decimal_Value` must be greater than zero. A value of zero will result in an undefined calculation and may cause ECU instability.

## Implementation Details

When modifying these values in the ECU binary, ensure the following:

* **Hex Conversion:** Convert the hexadecimal byte found in the ROM to a decimal value before applying the formula.
* **Resolution:** Because the value is stored as a single 8-bit byte, the resolution is limited to 256 possible values (0–255). This results in non-linear RPM increments as the decimal value decreases.
* **Verification:** Always verify the resulting RPM against the physical engine's mechanical limits to prevent over-revving.

## Common Reference Values

| Decimal Value | Calculated RPM |
| :--- | :--- |
| 231 | 8,000 |
| 210 | 8,800 |
| 192 | 9,625 |
| 185 | 9,989 |

> [!TIP]
> To calculate the required hex value for a target RPM, rearrange the formula to: `Decimal_Value = 1,848,000 / Target_RPM`. Round the result to the nearest whole number.