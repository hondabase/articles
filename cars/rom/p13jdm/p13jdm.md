---
summary: 'Technical reference for P13 JDM ECU memory mapping, including RAM locations and ROM-based rev limit calculations.'
tags: [tuning, rom, sensors, reference, p13]
applies_to:
  models: [prelude]
  chassis: [bb]
complexity: intermediate
---

# P13 JDM ECU Memory Map

## RAM Locations

| Location | Bytes | Description | Notes |
| :--- | :--- | :--- | :--- |
| - | - | - | - |

## ROM Locations

| Location | Bytes | Description | Notes |
| :--- | :--- | :--- | :--- |
| 2EC1 | 1 | Rev Limit | Desired RPM / 45.18 = 8-bit decimal value. Convert to Hex and store at 2EC1. |

> [!TIP]
> To calculate the hex value for the rev limit, divide your target RPM by 45.18, then convert the resulting decimal value to hexadecimal.
