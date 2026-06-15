---
summary: 'Absolute Pressure refers to pressure measurements made on a scale where Absolute Vacuum = 0. Atmospheric Pressure is approximately 14.'
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Absolute Pressure'
    url: /pgmfi/wiki/library/absolute-pressure
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Absolute Pressure

Absolute Pressure refers to pressure measurements made on a scale where [Absolute Vacuum](/cars/sensors/absolute-vacuum) = 0. *

- [Atmospheric Pressure](/cars/wiring/atmospheric-pressure) is approximately 14.7psi at sea level, measuring absolute pressure.
- 10psi of [Boost](/cars/rom/boost) is approximately 24.7psi (14.7 psi [Atmospheric Pressure](/cars/wiring/atmospheric-pressure) + 10psi [Boost](/cars/rom/boost))at sea level, measuring absolute pressure.
- Similarly, 30psi on the tire guage for your car is approximately 44.7psi [Absolute Pressure](/cars/diagnostics/absolute-pressure)(14.7 psi [Atmospheric Pressure](/cars/wiring/atmospheric-pressure) + 30psi tire pressure).

---

An editor that displays in [Absolute Pressure](/cars/diagnostics/absolute-pressure) looks like this: ![abs_pressure_crome.jpg](abs_pressure_crome.jpg)Column 10 is approximatly atmospheric pressure, slightly less due either to interpolation or the fact that even at [WOT](/cars/reference/wot) there will be some vaccuum. Column 1 is somewhat arbitrary, and not true zero aka absolute vaccuum. See also [Map Sensor](/cars/fueling/map-sensor) for the values the OEM [Map Sensor](/cars/fueling/map-sensor) is capable of reading.
