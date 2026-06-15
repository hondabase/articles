---
summary: 'Peak And Hold Injectors aka Low Impedance Injectors. Impedance typically ~25ohms. At 12volts, this is a draw of ~62.'
tags: [ecu, reference, sensors, wiring, conversion]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Peak And Hold Injectors'
    url: /pgmfi/wiki/library/peak-and-hold-injectors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Peak And Hold Injectors

[Peak And Hold Injectors](/cars/wiring/peak-and-hold-injectors) aka [Low Impedance Injectors](/cars/fueling/low-impedance-injectors). Impedance typically ~2-5ohms. At 12volts, this is a draw of ~6-2.4 amps The high current will cause the injectors to run hotter. The peak current opens the injector "crisply" and decisively. Then a lower "Hold" current keeps the injector open. To run these injectors with the honda ECU, you may need to use an inline [Resistor Box](/cars/wiring/resistor-box). [OBD0](/cars/rom/obd0) already has a resistor box wired in. [OBD1](/cars/wiring/obd1) does not have a [Resistor Box](/cars/wiring/resistor-box). [OBD2](/cars/wiring/obd2) does not have a [Resistor Box](/cars/wiring/resistor-box).
