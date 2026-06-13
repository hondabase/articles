---
summary: 'Honda ECUs are engineered with many levels of redundancy. There is a Backup processor (labeled NEC BACK0004 in most OBD0 and Oki 6534 in most OBD1 (??)).'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - diagnostics
---

# ECU Backup Processor

Honda [ECU](/cars/electronics/ecu)s are engineered with many levels of redundancy. There is a Backup processor (labeled NEC BACK0004 in most [OBD](/cars/electronics/obd)0 and Oki 6534 in most [OBD](/cars/electronics/obd)1 (??)). The backup processor is resposible for running the car when the [ECU](/cars/electronics/ecu) has detected a severe fault, as usually indicated by a "solid" [CEL](/cars/electronics/cel). It does not use the full array of sensors that the car has, and is intended to minimally allow the car to move under its own power in the event of a "total" failure of main [ECU](/cars/electronics/ecu) logic.
