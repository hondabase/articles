---
summary: 'The 1wire VTEC codebase is a ROM for the OBD0 MPFI ECUs that allows the Automatic Transmission Lockup Solenoid to be used to control VTEC engagement.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: '1 Wire Vtec'
    url: /pgmfi/wiki/library/1-wire-vtec
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# 1 Wire VTEC

The 1-wire VTEC codebase is a [ROM](/cars/rom/rom) for the [OBD0 MPFI](/cars/diagnostics/obd0mpfi) [ECU](/cars/ecu/ecu)s that allows the [Automatic Transmission Lockup Solenoid](/cars/sensors/automatic-transmission-lockup-solenoid) to be used to control VTEC engagement. Jason Parker came up with the [Hardware For One Wire VTEC](/cars/rom/hardware-for-one-wire-vtec) changes. As of Oct 2 2003 it is functional but needs some help and further testing. Dave Blundell has several cars running around on it. If you want to contribute/work/see it, check out the ***1w_vtec*** code module from [Source Forge](/cars/wiring/source-forge)
