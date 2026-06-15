---
summary: 'Relative Pressure is when you disregard that we are at all times surrounded by atmospheric pressure (approximatley 14.'
tags: [tuning, rom, sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Relative Pressure'
    url: /pgmfi/wiki/library/relative-pressure
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Relative Pressure

[Relative Pressure](/cars/rom/relative-pressure) is when you disregard that we are at all times surrounded by atmospheric pressure (approximatley 14.5psi). Therefore if a container is said to contain 10psi relative pressure, it's aboslute pressure will truly be 10psi + 14.5 == 24.5psi. ---

An editor that displays in [Relative Pressure](/cars/rom/relative-pressure) looks like this: ![rel_pressure_uber.jpg](rel_pressure_uber.jpg)Column 10 is approximatly atmospheric pressure, slightly less due either to interpolation or the fact that even at [WOT](/cars/reference/wot) there will be some vaccuum. Column 1 is somewhat arbitrary, and not true zero aka absolute vacuum. See also [Map Sensor](/cars/fueling/map-sensor) for the values the OEM [Map Sensor](/cars/fueling/map-sensor) is capable of reading.
