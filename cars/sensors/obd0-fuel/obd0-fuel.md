---
summary: 'Technical reference for the OBD0 fuel calculation formula, including pulsewidth derivation and variable definitions.'
tags: [ecu, fuel, obd0, tuning, reference]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 Fuel Calculation Formula

The OBD0 fuel pulsewidth calculation is determined by the relationship between the decimal value at the memory address and the column multiplier.

## Fuel Formula

The pulsewidth in milliseconds (ms) is calculated using the following formula:

**pulsewidth (ms) = (Dec At Addy + (224/a)) / (208/a)**

### Variable Definitions

*   **a**: The multiplier constant, defined as `2 ^ Column Multiplier`.
*   **Dec At Addy**: The raw decimal value retrieved from the specific fuel map memory address.

> [!NOTE]
> The **Column Multiplier** is a specific ROM parameter used to scale fuel map values. Ensure the correct multiplier is identified for the specific ROM bin being analyzed.

## Reference Data

| Variable | Description |
| :--- | :--- |
| **a** | Calculated multiplier constant |
| **Dec At Addy** | Raw decimal value from ECU memory |
| **224** | Constant offset for pulsewidth calculation |
| **208** | Constant divisor for pulsewidth calculation |

{{> fuel-calculation-notes }}
