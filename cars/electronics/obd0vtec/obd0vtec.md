---
summary: 'RPM conversion formula for OBD0 and OBD1 VTEC activation values.'
applies_to:
  obd: [0, 1]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
---

# OBD0 & OBD1 VTEC RPM Formula

In OBD0 and OBD1 Honda VTEC ECUs, the VTEC engagement and disengagement thresholds are determined using the following formula:

`RPM = (Decimal_Value - 128) * 62.52`

Where:
*   `Decimal_Value` is the base-10 value of the byte located at the VTEC RPM activation/deactivation addresses in the ROM.
