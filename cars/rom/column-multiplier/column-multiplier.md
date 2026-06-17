---
summary: 'The column multiplier is a critical value used in fuel map calculations, located immediately following the fuel map data in the ROM.'
tags: [tuning, rom, fuel-map, calibration]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Understanding the ECU Fuel Map Column Multiplier

The column multiplier is a scalar value used in the calculation formula for individual columns within an ECU fuel map. These multipliers are stored in the ROM immediately following the fuel map data.

## Data Structure and Location

The multipliers are mapped sequentially to the fuel map columns. The first value following the fuel map corresponds to column 1, the second value to column 2, and so on.

> [!IMPORTANT]
> Ensure that the multiplier values are correctly identified during ROM editing. Incorrect values will result in improper fuel scaling across the entire load or RPM range associated with that specific column.

## Calculation Reference

The ECU utilizes these multipliers to scale raw fuel map data into usable pulse-width values. When modifying fuel maps, verify that the column multipliers remain within the operational limits defined by the specific ECU architecture to prevent lean or rich conditions.

### Multiplier Mapping Table

| Map Column | Multiplier Location |
| :--- | :--- |
| Column 1 | First byte/word after map |
| Column 2 | Second byte/word after map |
| Column 3 | Third byte/word after map |
| Column N | Nth byte/word after map |

> [!TIP]
> Use a hex editor or tuning software with defined map offsets to visualize these multipliers. They are typically located immediately after the final row of the fuel table in the binary file.