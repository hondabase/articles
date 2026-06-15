---
summary: 'First of all i''ll thank NicoHRED again for the info he posts in the general forum about the "66P507 Readout".'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Oki66207 Reader-DIP64'
    url: /pgmfi/wiki/library/obd1-oki66207-reader-dip64
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 Oki66207 Reader-DIP64

First of all i'll thank Nico-HRED again for the info he posts in the general forum about the "`66P507` Readout". I adapted the idea and simplified it, so everyone of us can now readout the content of his `66207`. My reader is a bit different of the one he posted. I need a [ECU](/cars/ecu/ecu) with a `66207`, a 27C512 (EProm), a 1 k Resistor, two wires and a RS232<->TTL converter. The most of you will allready have this, if not, the parts are usual and cheep. We need to modify the [ECU](/cars/ecu/ecu) a bit to have a nice `66207` reader, here is a short description:

- If your [ECU](/cars/ecu/ecu) isn't chipped, you need to add the `74HC373`, the EProm socket and the 1kOhm resistor (`R54`).
- Connect a wire from the `66207` pin 16 (A15) to the Eprom Pin 1 (A15).

BUT DON'T PUT THE PIN 1 OF THE [EPROM](/cars/rom/eprom) IN THE SOCKET! JUST CONNECT THE WIRE TO IT. - Connect a wire from the `66207` Pin 19 (P2.2) to the `66207` Pin 27 (-EA).
- Remove the Jumper `J1` and replace it with a 1kOhm resistor.
- Put in the 27C512 Eprom, programmed with my "ROMREADER" program on it.
- Connect your PC via a RS232<->TTL converter to the [ECU](/cars/ecu/ecu) (see [Data Logging](/cars/diagnostics/data-logging) for more information).

Let's read a `66207`: - Switch off your [ECU](/cars/ecu/ecu), or leave it off.
- Start the program on the PC: DOWNLOADER
- if the Address display isn't 0000, then click on RESET.
- Switch on your [ECU](/cars/ecu/ecu)
- After around 1 secound you should see the address counter running
- after almost a minute (i never stopped it) the address counter should show 8001
- now click SAVE to save your rom.

If something dosn't work, retry the procedure but don't forget to click on RESET. Now have fun with your own `66207` reader. Doc | **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/zip.gif) [downloader.zip](downloader.zip) | mod | 225127 | 05 Mar 2004 - 18:09 | blundar | Win32 downloader application | | ![](/pgmfi/wiki/assets/icn/else.gif) [romreader66207.bin](romreader66207.bin) | mod | 65536 | 05 Mar 2004 - 18:10 | blundar | BIN file to use for reading [MCU](/cars/rom/mcu) | | ![](/pgmfi/wiki/assets/icn/txt.gif) [romreader.txt](romreader.txt) | mod | 2212 | 05 Mar 2004 - 18:10 | blundar | Assembly source of reader program | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [66207\\_romreader.jpg](66207_romreader.jpg) | mod | 57642 | 05 Mar 2004 - 18:10 | blundar | Picture of hardware modifications |
