---
summary: 'Aka "Limp Home Mode" Limp Mode is the mode of operation when the ECU''s CEL is lit solid red indicating a major malfunction.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# Limp Mode

Aka "Limp Home Mode" [Limp Mode](/cars/electronics/limp-mode) is the mode of operation when the [ECU](/cars/electronics/ecu)'s [CEL](/cars/electronics/cel) is lit solid red indicating a major malfunction. It is intended to get the car home, and will run the car very poorly. The backup processor is running the car without using [ROM](/cars/electronics/rom) at this point. Only the TDCSensor and [TPS Sensor](/cars/electronics/tps-sensor) are used in this mode. Revlimit is encountered at 3500rpm. More info:

- [OBD0 BACKUP](/cars/electronics/obd0backup)

NOTE: It would be nice to have a list of which sensor will/will not trigger [Limp Mode](/cars/electronics/limp-mode)
