---
summary: 'Author: doc 071003 15:21 Did i? Ok, in a 203 or 209 rom, you can change the location 6010 (hex) from 00 to FF to bypass the VSS check in the VTEC routine.'
applies_to:
  obd: [0, 1, 2]
  ecus: [P30]
complexity: advanced
tags:
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
  - ecu
---

# Disable VTEC VSS Check P30 203

Author: doc 07-10-03 15:21 Did i? Ok, in a 203 or 209 rom, you can change the location 6010 (hex) from 00 to FF to bypass the [VSS](/cars/electronics/vss) check in the VTEC routine. If you use a other rom, you've to search for the right location. Here a short instruction how i would search for it: First we need a disassembly of the desired rom. Choose your faforite disassembler and create the disasm. Search for the VTEC routine. I'll normally search for "22.1", with a1k0n's disassembler you've to search for "`22h`.1" (don't confuse with *OFF* 22.1) and stop when i find a routine which looks similar to the following one (the addresses and offset could be different, but the RB 22.1 and RB 22.0 are in every Rom the same!):

- 11B9- `C5` 22 09 : RB 22.1 ; Reset Bit Port1.1 VTEC
- 11BC- CB 24 : SJ 11E2 ; disable VTEC

---

- 11BE- C5 22 19 : SB 22.1 ; Set Bit Port1.1
- 11C1- C5 E9 C0 32 : CMPB E9, #32
- 11C5- CA 1B : JLT 11E2
- 11C7- C5 C1 C0 44 : CMPB C1, #44
- 11CB- CD 15 : JGE 11E2

---

- 11CD- 90 9D 10 60 : LCB A, 6010 ; use [VSS](/cars/electronics/vss)
- 11D1- CE 03 : JNE 11D6
- 11D3- D8 28 0C : JBR off 28.0, 11E2 ; enough speed for VTEC?
- 11D6- DB 16 03 : JBR off 16.3, 11DC
- 11D9- ED 11 03 : JBS off 11.5, 11DF
- 11DC- E9 28 0B : JBS off 28.1, 11EA
- 11DF- E9 1F 21 : JBS off 1F.1, 1203

---

- 11E2- C5 22 08 : RB 22.0 ; }
- 11E5- C4 1F 0A : RB off 1F.2 ; } deactive VTEC
- 11E8- CB 29 : SJ 1213 ; }

---

To activate VTEC without taking care about the speed sensor we're interrested in the following lines: - 11CD: LCB A,6010 ;Here the [ROM](/cars/electronics/rom) Content on address 6010 is readed into A. (hardcoded configuration)
- 11D1: JNE 11D6 ;If the [ROM](/cars/electronics/rom) Content is not 00 then jump to 11D6
- 11D3: JBR off 28.0, 11E2 ;If off 28.0=0 then jump to 11E2 (off 28.0 will be set in a [VSS](/cars/electronics/vss) check routine.)

Now you can decide how to patch your Rom. Change Rom Address 6010 (or whatever you find in your rom) from 00 to FF, overjump the [VSS](/cars/electronics/vss) check (11CD: J 11D6), or whatever (i.e. 11D3: NOP, NOP, NOP) ... Hope this helps. Doc
