---
summary: 'This page explain how to replace the current 5128 XRAM 2K SRAM chip by a DS1220 NVSRAM for future RTP solution.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - wiring
  - conversion
  - diagnostics
---

# Replace M5128

This page explain how to replace the current [5128 XRAM](/cars/electronics/5128xram) 2K [SRAM](/cars/electronics/sram) chip by a DS1220 [NVSRAM](/cars/electronics/nvsram) for future [RTP](/cars/electronics/rtp) solution.

- Brief Explanation
- Parts list:
- Construction:
- Step by step:
- Note:

###  Brief Explanation 

 The M5128 chip is used to store and calculate values while the car is running. By default pin 19 and 22 are grounded, thus preventing full 2k addressing. Also, it is a good idea to replace the current M5128 by a DS1220 [NVSRAM](/cars/electronics/nvsram) module. This module behave like a normal ram, but its [RAM](/cars/electronics/ram) content will remain when power is cut. ###  Parts list: 

- 1x DS1220AB
- 1x 24 pin IC socket
- 22 gauge wire (or smaller)

###  Construction: 

 It is pretty simple, but required a bit of dexterity. First you need to unsolder the M5128. Then, you should cut the traces of pin 19 an dpin 22 as they both connect to the ground. Solder the 24 pin IC socket. Then, solder a wire from M5128 pin 19 to [MCU](/cars/electronics/mcu) pin 23 and solder a wire from M5128 pin 22 to [MCU](/cars/electronics/mcu) pin 22 too. ###  Step by step: 

- Desolder M5128
- Cut traces to ground of pin 19 and pin 22
- Solder 24 pin IC socket
- Solder wire from M5128 pin 19 to [MCU](/cars/electronics/mcu) pin 23
- Solder wired from M5128 pin 22 to [MCU](/cars/electronics/mcu) pin 22
- Put in the DS1220AB

###  Note: 

The traces to be cut on a 90-91 [ECU](/cars/electronics/ecu) are on the component side. On the 88-89, there is 1 trace on the solder side, and 1 on the component side. You can check out the scans to help you out. | **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [DS1220-88-89.jpg](DS1220-88-89.jpg) | mod | 681906 | 27 Feb 2004 - 17:48 | synoptic | Solder side of a 1988 - 1989 [ECU](/cars/electronics/ecu) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [DS1220-90-91.jpg](DS1220-90-91.jpg) | mod | 728209 | 27 Feb 2004 - 17:49 | synoptic | Solder side of a 1990 - 1991 [ECU](/cars/electronics/ecu) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [DS1220-TOP-90-91.jpg](DS1220-TOP-90-91.jpg) | mod | 115939 | 27 Feb 2004 - 17:50 | synoptic | Component side of a 1990 - 1991 [ECU](/cars/electronics/ecu) |
