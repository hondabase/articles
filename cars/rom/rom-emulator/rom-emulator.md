---
summary: 'ROM Emulators "look" like a ROM to whatever you connect them to. In most cases here, that would normally be an ECU.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rom Emulator'
    url: /pgmfi/wiki/library/rom-emulator
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ROM Emulator

[ROM](/cars/rom/rom) Emulators "look" like a [ROM](/cars/rom/rom) to whatever you connect them to. In most cases here, that would normally be an [ECU](/cars/ecu/ecu). The most important feature of a [Rom Emulator](/cars/rom/rom-emulator) compared to an [EPROM](/cars/rom/eprom) or even [FLASH](/cars/rom/flash)-[ROM](/cars/rom/rom) is that you can change the data that a [ROM](/cars/rom/rom) Emulator contains on the fly, while it is running. Most often, this is accomplished using [SRAM](/cars/sensors/sram)/NVSRAM coupled with a bunch of logic gates or a FPGA to avoid crunching data. the [Xtronics Romulator](http://web.archive.org/web/20260528071037/https://xtronics.com/) is the most commonly heard of [Rom Emulator](/cars/rom/rom-emulator) as it is endorsed by [Hon Data](/cars/diagnostics/hon-data) for use with their products.
