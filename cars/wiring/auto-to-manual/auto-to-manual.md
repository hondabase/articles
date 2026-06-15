---
summary: 'Most automatic ECUs can be converted to a 5spd rather easily. Going the other way often involves adding more components.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0, 1, 2]
  brand: Acura/Honda
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Auto To Manual'
    url: /pgmfi/wiki/library/auto-to-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Auto To Manual

Most automatic [ECU](/cars/ecu/ecu)s can be converted to a 5spd rather easily. Going the other way often involves adding more components. At this time, it appears that the conversion can be done in either software OR hardware: most of the "mugen" [ROM](/cars/rom/rom)s disable the check for automatic transmission hardware, letting an automatic [ECU](/cars/ecu/ecu) run a 5spd engine w/o throwing a code 19 (auto trans lockup solenoid) You can also modify the hardware to make and auto [ECU](/cars/ecu/ecu) think it is a Manual. This is rather specific to `each` [ECU](/cars/ecu/ecu).

- [OBD0 ECU AUTO TO MANUAL WITHOUT REMOVE ANY HARDWARE](/cars/wiring/obd0ecuautotomanualwithoutremoveanyhardware) = How to Run Auto ECU WITHOUT Check Engine!
- [PS9 Auto Manual](/cars/sensors/ps9-auto-manual) = How to turn a [OBD0](/cars/rom/obd0) PS9, PG7, PM7, PR5 or similar circuit boards into a PM6-ish manual [ECU](/cars/ecu/ecu)
- OBD0 PR4 Auto Manual = Converting an auto [OBD0](/cars/rom/obd0) PR4 to manual
- [PR3 Auto Manual](/cars/ecu/pr3-auto-manual) = Converting an auto PR3 to manual
- [OBD1 Civic Integra Auto Manual](/cars/wiring/obd1-civic-integra-auto-manual) = Converting an automatic 92-95 Civic and Integra [ECU](/cars/ecu/ecu) from auto to manual
- [OBD1 P08 Auto Manual](/cars/sensors/obd1p08-auto-manual) = Converting an automatic P08 or P30 [JDM](/cars/sensors/jdm) (mini style) [ECU](/cars/ecu/ecu) from auto to manual
- [OBD1 P13 Auto Manual](/cars/wiring/obd1p13-auto-manual) = Converting a 92-95 H22A prelude [ECU](/cars/ecu/ecu) from auto to manual
- [OBD2 P5 MAuto Manual](/cars/wiring/obd2p5m-auto-manual) = Converting a 97-01 H22A Prelude PCM from auto to manual
