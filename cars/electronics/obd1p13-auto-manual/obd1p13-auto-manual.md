---
summary: 'Most Auto Ecus have a jumper at RP11 and have a blank space at RP12. Move RP11 to RP12 and you now have a Manual ECU.'
applies_to:
  obd: [1]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - wiring
  - conversion
---

# OBD1P13 Auto Manual

Most Auto Ecus have a jumper at RP11 and have a blank space at RP12. Move RP11 to RP12 and you now have a Manual [ECU](/cars/electronics/ecu). Here a closeup of the [JDM](/cars/electronics/jdm) Jumper configuration: [Auto Jumpers](/pgmfi/wiki/media/library/P13/JDM-p13-resistors.jpg) R96, C49 and R82 seem to be related to some Auto trans controls but can be left in place. Some [ECU](/cars/electronics/ecu)s (Like the [JDM P13-900](/pgmfi/wiki/media/library/P13/P13-900_jumpers.jpg)) have resistors in both places. You can just remove both of them and replace RP12 with a jumper wire. This applies to all [ECU](/cars/electronics/ecu)s that share the same board (P11, P12, P13, P14 and P39)
