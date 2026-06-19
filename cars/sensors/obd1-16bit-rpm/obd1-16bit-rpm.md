---
summary: 'Technical reference for calculating 16-bit RPM values in OBD1 Honda ECUs, including the conversion formula and byte order specifications.'
tags: [ecu, reference, sensors, obd1]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# OBD1 16-bit RPM Calculation Reference

To calculate the engine speed from a raw 16-bit RPM value retrieved from an OBD1 ECU, use the following conversion formula:

**RPM(x) = 1,875,000 / x**

Where **x** represents the raw 16-bit value.

> [!IMPORTANT]
> All 16-bit values in OBD1 ECUs are stored in **Little Endian** byte order. When reading raw data, ensure the least significant byte (LSB) and most significant byte (MSB) are processed in the correct sequence.
