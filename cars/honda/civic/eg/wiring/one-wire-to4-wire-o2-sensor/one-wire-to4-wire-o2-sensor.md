---
summary: 'If you have an ECU that lacks the O2 heater circuitry such as a P05, it is easy to enable this functionality.'
tags: [ecu, reference, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [civic]
  chassis: [eg]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'One Wire To4 Wire O2 Sensor'
    url: /pgmfi/wiki/library/one-wire-to4-wire-o2-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# One Wire To4 Wire O2 Sensor

If you have an [ECU](/cars/ecu/ecu) that lacks the O2 heater circuitry such as a P05, it is easy to enable this functionality. To convert a P05 to pretty much anything else, you need to add a transistor to enable the O2 sensor heater or you will throw a code. `Q30` needs to be added - [C144](/cars/sensors/c144) is its value. For [JDM](/cars/sensors/jdm) [ECU](/cars/ecu/ecu)s that lack the O2 heater circuitry, such as the P08, simply add a SMT version of the 2N4401 (general purpose NPN switching transistor) to location `Q15` on the underside of the [PCB](/cars/wiring/pcb). The proper part number for the transistor is MMBT4401, and they are readily available through retail suppliers such as [http://web.archive.org/web/20260612163410/https://www.digikey.com/](http://web.archive.org/web/20260612163410/https://www.digikey.com/)
