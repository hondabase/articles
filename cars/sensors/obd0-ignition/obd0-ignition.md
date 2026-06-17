---
summary: 'Technical reference for the ignition timing conversion formula used in OBD0 Honda ECU ROM mapping.'
tags: [ecu, tuning, ignition, obd0]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 Ignition Timing Conversion Formula

To convert raw hexadecimal data from an OBD0 Honda ECU ROM into usable ignition advance values, use the following calculation.

## Calculation Formula

The ignition advance in degrees is derived from the raw byte value stored at the specific ignition map memory address:

**Ignition Advance (Degrees) = (Decimal_Value - 15) * 0.36**

### Variables
* **Decimal_Value:** The base-10 integer representation of the hexadecimal byte found at the ignition map offset.

> [!NOTE]
> This formula applies specifically to standard OBD0 ROM structures. Ensure your map offsets are correctly identified before applying this conversion.

> [!TIP]
> When working with hex editors, ensure you convert the hex byte to decimal before subtracting 15 to avoid calculation errors.