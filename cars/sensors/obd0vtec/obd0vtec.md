---
summary: 'Calculate VTEC engagement and disengagement thresholds for OBD0 and OBD1 Honda ECUs using the standard RPM conversion formula.'
tags: [ecu, tuning, vtec, rom]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: beginner
---

# OBD0 and OBD1 VTEC RPM Calculation Formula

VTEC engagement and disengagement thresholds in OBD0 and OBD1 Honda ECUs are stored as single-byte hexadecimal values in the ROM. These values must be converted to decimal and processed through a specific formula to determine the actual RPM trigger point.

## Calculation Formula

Use the following formula to convert the ROM byte value to engine RPM:

**RPM = (Decimal_Value - 128) * 62.52**

### Variables
* **Decimal_Value:** The base-10 integer representation of the hexadecimal byte found at the VTEC activation or deactivation memory address.

> [!IMPORTANT]
> Ensure the hexadecimal value is converted to decimal before performing the subtraction. If the resulting value is negative, the threshold is effectively set below the engine's idle range.

## Reference Table

| Hex Value | Decimal Value | Calculated RPM |
| :--- | :--- | :--- |
| 0x80 | 128 | 0 |
| 0x90 | 144 | 1,000 |
| 0xA0 | 160 | 2,000 |
| 0xB0 | 176 | 3,000 |
| 0xC0 | 192 | 4,000 |
| 0xD0 | 208 | 5,000 |
| 0xE0 | 224 | 6,000 |
| 0xF0 | 240 | 7,000 |

> [!TIP]
> When tuning, always ensure the VTEC engagement RPM is set higher than the disengagement RPM to prevent "VTEC hunting" or rapid cycling of the solenoid.