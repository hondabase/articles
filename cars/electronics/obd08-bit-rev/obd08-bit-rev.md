---
summary: '8-bit rev limit and engine speed restart formula for OBD0 VTEC Honda ECUs.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
---

# OBD0 8-Bit Rev Limit Formula

For OBD0 Honda VTEC ECUs, the rev limit thresholds and recovery/restart speeds are calculated using the following 8-bit formula:

`RPM = 1848000 / Decimal_Value`

Where:
*   `Decimal_Value` is the base-10 value of the byte at the rev limit address.
