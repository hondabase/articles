---
summary: 'Dave Blundell sez "Vernon (deluded) sent me much of this info." As a rule of thumb, 90 PR4s have external PA sensors, and 91 ECUs have internal PA sensors.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  ecus: [PR4]
  models: [integra]
  chassis: [da, dc2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Adjust PR4 Pa Sensor'
    url: /pgmfi/wiki/library/adjust-pr4-pa-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adjust PR4 Pa Sensor

Dave Blundell sez "Vernon (deluded) sent me much of this info." As a rule of thumb, 90 PR4s have external PA sensors, and 91 [ECU](/cars/ecu/ecu)s have internal PA sensors. You can tell (to some degree) by looking at the "code" of the [ECU](/cars/ecu/ecu): | **Label** | **Description** | | :--- | :--- | | A00 | 90 5 Speed (-33 program) | | A01 | 90 5 Speed (?? program) | | A02 | 90 5 Speed (-54 program) | | A51 | 90 Automatic (?? program) | | A52 | 90 Automatic (-54 program) | | A10 | 91 5 Speed (-92 program) | | A12 | 91 5 speed (-92 program) | | A60 | 91 auto (-92 program) | | A62 | 91 auto (-92 program) | Ok, with that out of the way... It is easy to select whether to use a internal or external [PA](/cars/rom/pressure-atmosphere) sensor. See the following table: | **Part** | **External PA** | **Internal PA** | | :--- | :--- | :--- | | PA Sensor | missing | installed | | `C103` | missing | present(103Z) | | `R92` | jumper | 10Kohm | | `C106` | missing | present(103Z) | ***edit***It seems that the Internal PA [ECU](/cars/ecu/ecu) is missing `C106`, and the External PA [ECU](/cars/ecu/ecu) has `C106` present.
