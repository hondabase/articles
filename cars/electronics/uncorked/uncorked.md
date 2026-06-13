---
summary: 'The stock code divides the Map Sensor reading by two. This caps the maximum pressure the ECU can respond to by half the maximum of what the Map Sensor is capable of reading.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# uncorked

The stock code divides the [Map Sensor](/cars/electronics/map-sensor) reading by two. This caps the maximum pressure the [ECU](/cars/electronics/ecu) can respond to by half the maximum of what the [Map Sensor](/cars/electronics/map-sensor) is capable of reading. By simply removing this division, we have uncorked the [Map Sensor](/cars/electronics/map-sensor) to read all the way up to 11psi of boost.
