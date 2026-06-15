---
summary: 'Aka "Limp Home Mode" Limp Mode is the mode of operation when the ECU''s CEL is lit solid red indicating a major malfunction.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Limp Mode'
    url: /pgmfi/wiki/library/limp-mode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Limp Mode

Aka "Limp Home Mode" [Limp Mode](/cars/diagnostics/limp-mode) is the mode of operation when the [ECU](/cars/ecu/ecu)'s [CEL](/cars/wiring/cel) is lit solid red indicating a major malfunction. It is intended to get the car home, and will run the car very poorly. The backup processor is running the car without using [ROM](/cars/rom/rom) at this point. Only the TDCSensor and [TPS Sensor](/cars/diagnostics/tps-sensor) are used in this mode. Revlimit is encountered at 3500rpm. More info:

- [OBD0 BACKUP](/cars/diagnostics/obd0backup)

NOTE: It would be nice to have a list of which sensor will/will not trigger [Limp Mode](/cars/diagnostics/limp-mode)
