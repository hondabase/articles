---
summary: 'Ignition timing advance conversion formula for 8-bit OBD1 Honda ECUs.'
applies_to:
  obd: [1]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
---

# OBD1 8-Bit Ignition Advance Formula

In 8-bit OBD1 Honda ECUs, the ignition advance value (in degrees) is calculated from the raw table byte value `v` using the following formula:

`Ignition Advance (Degrees) = (v - 24) / 4`

Where:
*   `v` is the decimal representation of the byte at the ignition map cell.
