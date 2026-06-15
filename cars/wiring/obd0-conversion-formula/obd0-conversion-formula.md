---
summary: 'Describe OBD0 Conversion Formula here. OBD016 Bit RPM is used for revlimiters, target idle and most other 16bit RPM values in the ROM.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Conversion Formula'
    url: /pgmfi/wiki/library/obd0-conversion-formula
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Conversion Formula

Describe [OBD0 Conversion Formula](/cars/wiring/obd0-conversion-formula) here.

- [OBD016 Bit RPM](/cars/diagnostics/obd016-bit-rpm) is used for revlimiters, target idle and most other 16bit [RPM](/cars/sensors/rpm) values in the [ROM](/cars/rom/rom).
- [OBD0 VSS](/cars/diagnostics/obd0vss) is used to convert the values in ram `06Ch` to Vehicle Speed.
- [OBD0 Fuel](/cars/sensors/obd0-fuel) is used to convert the hex values in the fuel maps to pulse width in milliseconds.
- [OBD0 Ignition](/cars/sensors/obd0-ignition) is used to convert the hex values in the ignition maps into degrees advance.
- [OBD0 VTEC](/cars/sensors/obd0vtec) is used for VTEC values.
- [OBD08 Bit Rev](/cars/sensors/obd08-bit-rev) is used for the [OBD0](/cars/rom/obd0) VTEC [ECU](/cars/ecu/ecu)s' revlimits.
