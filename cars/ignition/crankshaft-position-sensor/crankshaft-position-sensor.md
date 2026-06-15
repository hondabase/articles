---
summary: 'The crank position (CKP) sensor and how the ECU uses it.'
tags: [sensor, ignition]
applies_to:
  models: [civic, crx, del-sol, integra, prelude, accord, s2000, nsx]
  chassis: [ef, eg, ek, da, dc2, bb, cb-cd, ap1, ap2, na1-na2]
sources:
  - name: 'pgmfi.org wiki'
    title: 'Crankshaft Position Sensor'
    url: /pgmfi/wiki/library/crankshaft-position-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Crankshaft Position Sensor

The crankshaft position (CKP) sensor tells the ECU how fast the engine is turning and where
it is in its rotation. The ECU uses that signal as the timing reference for both fuel
injection and ignition, so without a good CKP signal the engine will not run.

On many older Hondas the crank, cylinder (CYP) and top-dead-centre (TDC) sensors are housed
together inside the distributor, reading toothed reluctor wheels turned by the camshaft. The
CKP wheel carries many teeth for fine resolution of engine speed, while the TDC and CYP
wheels use fewer teeth to mark specific cylinder positions.

## Related

- [Cylinder position sensor](/cars/sensors/cylinder-position-sensor)
- [ECU sensors](/cars/sensors/ecu-sensors)
