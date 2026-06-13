---
summary: 'ROM Emulators "look" like a ROM to whatever you connect them to. In most cases here, that would normally be an ECU.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# ROM Emulator

[ROM](/cars/electronics/rom) Emulators "look" like a [ROM](/cars/electronics/rom) to whatever you connect them to. In most cases here, that would normally be an [ECU](/cars/electronics/ecu). The most important feature of a [Rom Emulator](/cars/electronics/rom-emulator) compared to an [EPROM](/cars/electronics/eprom) or even [FLASH](/cars/electronics/flash)-[ROM](/cars/electronics/rom) is that you can change the data that a [ROM](/cars/electronics/rom) Emulator contains on the fly, while it is running. Most often, this is accomplished using [SRAM](/cars/electronics/sram)/NVSRAM coupled with a bunch of logic gates or a FPGA to avoid crunching data. the [Xtronics Romulator](https://www.xtronics.com) is the most commonly heard of [Rom Emulator](/cars/electronics/rom-emulator) as it is endorsed by [Hon Data](/cars/electronics/hon-data) for use with their products.
