---
summary: 'ZIF stands for Zero Insertion Force. ZIF sockets are commonly used in ECUs where the EEPROM will be removed and reinserted frequently.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: ZIF
    url: /pgmfi/wiki/library/zif
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ZIF

[ZIF](/cars/rom/zif) stands for Zero Insertion Force. [ZIF](/cars/rom/zif) sockets are commonly used in [ECU](/cars/ecu/ecu)s where the [EEPROM](/cars/diagnostics/eeprom) will be removed and reinserted frequently. "ZIFing an [ECU](/cars/ecu/ecu)" is when you desolder the stock [EEPROM](/cars/diagnostics/eeprom) and solder a [ZIF](/cars/rom/zif) socket in its place. Ensure that you choose a [ZIF](/cars/rom/zif) socket that has the same number of pins as your [EEPROM](/cars/diagnostics/eeprom). Keep in mind that some [ZIF](/cars/rom/zif) sockets are physically larger then regular IC sockets. If the IC you want to add a [ZIF](/cars/rom/zif) socket to has many parts right next to it, it may not fit. Double-check before ordering... 36-pin: ![ELK040b.jpg](http://www.progshop.com/photos/ELK040b.jpg)28-pin: (digikey part

# A347-ND, [Future Active](/cars/sensors/future-active) carries them much cheaper for tubes) ![](http://www.moates.net/imagery/gmecm/hardware/s4.jpg)
