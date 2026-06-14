---
summary: 'Dave says: Well, borrowing an idea from NicoHRED/Doc used in the 66Ks, here is a program that should read out the contents of a 83C154 MCU.'
applies_to:
  obd: [0]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# OBD0 Oki83C154 Reader

Dave says: Well, borrowing an idea from Nico-HRED/Doc used in the 66Ks, here is a program that should read out the contents of a `83C154` [MCU](/cars/electronics/mcu). It assumes that you have the [MCU](/cars/electronics/mcu) connected to an external [EPROM](/cars/electronics/eprom). The program jumps to `4100h`, and then dumps the contents of the first 16K of memory after flipping [_EA](/cars/electronics/ea) to mask the internal [ROM](/cars/electronics/rom) onto 0000-`4000h`. The use of a `MAX233` serial conversion board is required. Doc says: for the hardware - you just need to open the -EA jumper and connect the -EA line of the processor to the P1.7 of the processor. (cause the P1.7 is initially LOW). On the DOWNLOADER, set serial to 4800,n,8,1. New feature in the downloader: show memory dump, and set the memory range to save. I've added this, cause the ODB1 ECU's send one junk byte over the serial when the [ECU](/cars/electronics/ecu) is powered on. The ODB0 don't do this. So you first take a look at the downloaded dump and decide what do you want to save. I dumped a PM5 (will post in the rom dumps) - looks funny, but have at least aignition and fuel table. So you ODB0 gurus can take a look on it. I think the tables are really small? cu, Doc ...

| **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/else.gif) [Read83C154\\_12mhz.bin](/pgmfi/wiki/media/library/OBD0Oki83C154Reader/Read83C154_12mhz.bin) | mod | 16711 | 05 Mar 2004 - 17:49 | blundar | BIN of code to dump [MCU](/cars/electronics/mcu) | | ![](/pgmfi/wiki/assets/icn/else.gif) [read83c154\\_12mhz.asm](/pgmfi/wiki/media/library/OBD0Oki83C154Reader/read83c154_12mhz.asm) | mod | 2733 | 05 Mar 2004 - 17:49 | blundar | assembly code of DASM | | ![](/pgmfi/wiki/assets/icn/exe.gif) [downloader.exe](downloader.exe) | mod | 522752 | 05 Mar 2004 - 17:49 | blundar | Win32 Dowloader application | | *Library.OBD0Oki83C154Reader moved from Library.OBD0Oki83C154ReaderBlundar on 05 Mar 2004 - 17:54 by Home.blundar* - [put it back](https://web.archive.org/web/http://www.pgmfi.org/twiki/bin/rename/Library/OBD0Oki83C154Reader?newweb=Library&newtopic=OBD0Oki83C154ReaderBlundar&confirm=on "Click to move topic back to previous location, with option to change references.") | | :--- |
