---
summary: 'Technical reference for calculating fuel pulse width in OBD0 Honda ECUs using the column multiplier and decimal address values.'
tags: [ecu, fuel, tuning, obd0]
complexity: beginner
---

# OBD0 Fuel Pulse Width Calculation

The fuel pulse width for OBD0 Honda ECUs is determined by the relationship between the column multiplier and the decimal value at the specific memory address.

## Calculation Formula

Use the following formulas to determine the fuel pulse width in milliseconds (ms):

1. **Calculate the multiplier (a):**
   `a = 2 ^ Column Multiplier`

2. **Calculate pulse width:**
   `Pulse Width (ms) = (Dec At Addy + (224 / a)) / (208 / a)`

> [!IMPORTANT]
> Ensure the **Column Multiplier** value is correctly identified from the ROM map before performing the calculation, as incorrect values will result in inaccurate pulse width scaling.

## Variable Definitions

| Variable | Description |
| :--- | :--- |
| **a** | Calculated multiplier based on the column multiplier value. |
| **Dec At Addy** | The decimal value retrieved from the specific ECU memory address. |
| **Pulse Width** | The final fuel injector duration in milliseconds (ms). |

{{> fuel-calculation-notes }}
