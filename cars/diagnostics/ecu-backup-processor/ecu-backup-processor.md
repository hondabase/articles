---
summary: 'Honda ECUs are engineered with many levels of redundancy. There is a Backup processor (labeled NEC BACK0004 in most OBD0 and Oki 6534 in most OBD1 (??)).'
tags: [ecu, reference, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Backup Processor'
    url: /pgmfi/wiki/library/ecu-backup-processor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ECU Backup Processor

Honda [ECU](/cars/ecu/ecu)s are engineered with many levels of redundancy. There is a Backup processor (labeled NEC BACK0004 in most [OBD](/cars/wiring/obd)0 and Oki 6534 in most [OBD](/cars/wiring/obd)1 (??)). The backup processor is resposible for running the car when the [ECU](/cars/ecu/ecu) has detected a severe fault, as usually indicated by a "solid" [CEL](/cars/wiring/cel). It does not use the full array of sensors that the car has, and is intended to minimally allow the car to move under its own power in the event of a "total" failure of main [ECU](/cars/ecu/ecu) logic.
