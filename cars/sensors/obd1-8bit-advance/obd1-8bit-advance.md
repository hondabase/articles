---
summary: 'Technical reference for calculating ignition timing advance values in 8-bit OBD1 Honda ECUs using the standard conversion formula.'
tags: [ecu, ignition, tuning, obd1]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# OBD1 8-Bit Ignition Advance Calculation

In 8-bit OBD1 Honda ECUs, the ignition advance value stored in the ignition maps is represented as a raw byte. To convert this hexadecimal or decimal byte value into degrees of ignition advance, use the following formula:

## Conversion Formula

**Ignition Advance (Degrees) = (v - 24) / 4**

### Variable Definitions
* **v**: The decimal representation of the byte value found in the ignition map cell.

> [!NOTE]
> The resulting value represents the total ignition advance in degrees BTDC (Before Top Dead Center).

## Reference Table

| Raw Byte (Hex) | Raw Byte (Dec) | Ignition Advance (Degrees) |
| :--- | :--- | :--- |
| 0x18 | 24 | 0.0° |
| 0x28 | 40 | 4.0° |
| 0x38 | 56 | 8.0° |
| 0x48 | 72 | 12.0° |
| 0x58 | 88 | 16.0° |
| 0x68 | 104 | 20.0° |
| 0x78 | 120 | 24.0° |

> [!IMPORTANT]
> Ensure that the byte value is converted from hexadecimal to decimal before applying the formula. Values below 24 (0x18) will result in negative values, which are typically not utilized in standard ignition timing maps.