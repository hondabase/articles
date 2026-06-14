---
summary: '"Chipping" an ECU means replacing the program running the ECU. Chipping is just slang. What we actually do is program (or "burn") a new bin file to the...'
applies_to:
  obd: [0]
complexity: intermediate
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
---

# What You Need

"Chipping" an [ECU](/cars/electronics/ecu) means replacing the program running the [ECU](/cars/electronics/ecu). Chipping is just slang. What we actually do is program (or "burn") a new bin file to the [ROM](/cars/electronics/rom) to replace the program currently running the [ECU](/cars/electronics/ecu). In order to chip an [ECU](/cars/electronics/ecu), you will need the following:

- [Soldering Iron](/cars/electronics/soldering-iron) - to solder chips in to the [ECU](/cars/electronics/ecu)
- [Desoldering Tool](/cars/electronics/desoldering-tool) - to remove chips/solder from an [ECU](/cars/electronics/ecu). A [Desoldering Iron](/cars/electronics/desoldering-iron), [Desoldering Braid](/cars/electronics/desoldering-braid), or a [Desoldering Station](/cars/electronics/desoldering-station) will also work. Read the [Desoldering Tips](/cars/electronics/desoldering-tips). If you are uncomfortable doing this, or dont have access to the tools, some of the PGMFI members will sell you a [ZIF](/cars/electronics/zif)-Socketed [ECU](/cars/electronics/ecu)
- [Rom Editor](/cars/electronics/rom-editor) - to create new bin file to burn to the Chip
- [Rom Burner](/cars/electronics/rom-burner) - to a chip to replace the stock program
- [ROM Library](/cars/electronics/ecu-definition-codes) - To get some ready made bins
- [Chips For ECUs](/cars/electronics/chips-for-ec-us) - to burn the new Bin file to - [the ATMEL AT29C256](/cars/electronics/29c256) seems to be the chip to get
- [Parts For ECUs](/cars/electronics/parts-for-ec-us)- is a fairly comprehensive list of the parts needed for [ECU](/cars/electronics/ecu)s.

Sounds pretty easy `eh`? Dave B. wrote a great [Introduction To ECUChipping](/cars/electronics/introduction-to-ecu-chipping) article that is an excellent place to start learning about chipping [ECU](/cars/electronics/ecu)s NOTE: [OBD0 MPFI](/cars/electronics/obd0mpfi) [ECU](/cars/electronics/ecu)s do not always have a [ROM](/cars/electronics/rom) for you to replace. Don't despair, [Chipping An88-89 ECU](/cars/electronics/chipping-an88-89ecu) is possible, too.
