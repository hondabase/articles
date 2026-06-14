---
summary: 'Ignition timing conversion formula for OBD0 Honda ECUs.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
---

# OBD0 Ignition Formula

In OBD0 Honda ECUs, the raw byte value stored in the ROM is converted to ignition advance degrees using the following formula:

`Ignition Advance (Degrees) = (Decimal_Value - 15) * 0.36`

Where:
*   `Decimal_Value` is the base-10 value of the byte located at the ignition map offset (often referred to as the value at the address).
