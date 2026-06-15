---
summary: "If ''x'' is a 16bit RPM value, then: RPM(''x'') = 1875000/''x'' 16bit values are invariably stored in Little Endian format on all OBD1 ECUs."
tags: [ecu, reference, sensors]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 16bit RPM'
    url: /pgmfi/wiki/library/obd1-16bit-rpm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 16bit RPM

If ''x'' is a 16-bit [RPM](/cars/sensors/rpm) value, then:

- [RPM](/cars/sensors/rpm)(''x'') = 1875000/''x''

16-bit values are invariably stored in [Little Endian](/cars/reference/little-endian) format on all [OBD1](/cars/wiring/obd1) [ECU](/cars/ecu/ecu)s.
