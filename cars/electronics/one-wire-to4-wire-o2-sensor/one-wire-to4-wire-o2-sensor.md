---
summary: 'If you have an ECU that lacks the O2 heater circuitry such as a P05, it is easy to enable this functionality.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# One Wire To4 Wire O2 Sensor

If you have an [ECU](/cars/electronics/ecu) that lacks the O2 heater circuitry such as a P05, it is easy to enable this functionality. To convert a P05 to pretty much anything else, you need to add a transistor to enable the O2 sensor heater or you will throw a code. `Q30` needs to be added - [C144](/cars/electronics/c144) is its value. For [JDM](/cars/electronics/jdm) [ECU](/cars/electronics/ecu)s that lack the O2 heater circuitry, such as the P08, simply add a SMT version of the 2N4401 (general purpose NPN switching transistor) to location `Q15` on the underside of the [PCB](/cars/electronics/pcb). The proper part number for the transistor is MMBT4401, and they are readily available through retail suppliers such as [http://www.digikey.com](http://www.digikey.com)
