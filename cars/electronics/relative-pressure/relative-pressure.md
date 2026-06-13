---
summary: 'Relative Pressure is when you disregard that we are at all times surrounded by atmospheric pressure (approximatley 14.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
---

# Relative Pressure

[Relative Pressure](/cars/electronics/relative-pressure) is when you disregard that we are at all times surrounded by atmospheric pressure (approximatley 14.5psi). Therefore if a container is said to contain 10psi relative pressure, it's aboslute pressure will truly be 10psi + 14.5 == 24.5psi. ---

An editor that displays in [Relative Pressure](/cars/electronics/relative-pressure) looks like this: ![rel_pressure_uber.jpg](rel_pressure_uber.jpg)Column 10 is approximatly atmospheric pressure, slightly less due either to interpolation or the fact that even at [WOT](/cars/electronics/wot) there will be some vaccuum. Column 1 is somewhat arbitrary, and not true zero aka absolute vacuum. See also [Map Sensor](/cars/electronics/map-sensor) for the values the OEM [Map Sensor](/cars/electronics/map-sensor) is capable of reading.
