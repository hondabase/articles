---
summary: 'A Checksum is a very basic form of error checking. A checksum is calculated by adding the values of a ROM together, without any form of carry or overflow checking.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference, diagnostics]
applies_to:
  obd: [0, 1]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Check Sum'
    url: /pgmfi/wiki/library/check-sum
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Check Sum

A Checksum is a very basic form of error checking. A checksum is calculated by adding the values of a [ROM](/cars/rom/rom) together, without any form of carry or overflow checking. Checksums can vary in size - 8bit, 16bit, 32bit checksums are all common. [OBD0](/cars/rom/obd0) and [OBD1](/cars/wiring/obd1) honda [ECU](/cars/ecu/ecu)s use exclusively 8 bit checksums i.e. checksums from 0 -> 255 decimal, 00-FF hex. There is a program called [check8](http://www.keil.com/download/files/check8.zip) (also available attached to this page) that can calculate 8bit checksums. You can update the rom so the checksum stays 00 even after editing it. Here is how to (using [Win Hex](/cars/rom/win-hex) in this example, but you can use the program posted below, but only to find checksum, not to edit the [ROM](/cars/rom/rom)) : Open [Win Hex](/cars/rom/win-hex) and select Tools Menu -> Calculate Hash (Select 8 bit). Write down the number it gives you. This is the current Checksum. Open Windows Calculator (Start -> Run -> Calc then press enter) View -> Scientific Select Hex Mode (or press F5) Do this : FF - Current_checksum ( FF - AB for example) The number it gives you is tu be written in a memory location, toward the bottom, where no code is present, and where the value FF is already there. Example : (FF - AB = 54) lets say I go to memory location 7FFF, value is FF. I replace FF by 54. if you dont have an address with a free FF value, but another value (lets say 00), use 00 in calc instead (00 - AB) and replace the free 00 with the result.

| **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/exe.gif) [Check8.exe](Check8.exe) | mod | 10308 | 05 Mar 2004 - 18:29 | blundar | Keil's 8 bit checksum utility |
