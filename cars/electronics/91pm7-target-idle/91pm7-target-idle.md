---
summary: 'Author: HRED Date: 010303 17:27 You can alter idle target : search "09c4" value you find for example in PM7FOR6121502.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# 91PM7 Target Idle

Author: HRED Date: 01-03-03 17:27 You can alter idle target : search "09c4" value you find for example in PM7FOR6_12-15-02.BIN rom a string with 6 rev values like this : 0A08 09C4 0964 0A77 09C4 0964 replace all values by this for 1000rpm idle target : 0753 0753 0753 0753 0753 0753 all values use the [OBD016 Bit RPM](/cars/electronics/obd016-bit-rpm) formula. Nicolas HRED France Bordeaux
