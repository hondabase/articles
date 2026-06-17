---
summary: 'An explanation of the Dec At Addy conversion process, which translates hexadecimal values stored at specific ECU memory addresses into their decimal equivalents.'
tags: [tuning, rom, sensors, reference, hex-to-decimal]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Understanding Dec At Addy

"Dec At Addy" refers to the decimal representation of a hexadecimal value stored at a specific memory address within the ECU. This conversion is essential when interpreting raw ROM data for tuning or diagnostic purposes.

## Conversion Logic

To determine the decimal value, identify the hexadecimal byte located at the target memory address and convert it to base-10.

**Example:**
*   **Target Address:** `1094h`
*   **Hex Value at Address:** `FF`
*   **Decimal Equivalent:** `255`

> [!TIP]
> Most scientific calculators or programming environments (such as Python or C++) can perform this conversion using the `int(value, 16)` function.

## Common Conversions

| Hexadecimal | Decimal |
| :--- | :--- |
| 00 | 0 |
| 0A | 10 |
| 64 | 100 |
| FF | 255 |

> [!IMPORTANT]
> Ensure you are referencing the correct memory bank or offset when reading values, as incorrect address targeting will result in erroneous data interpretation.