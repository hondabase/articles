---
summary: 'Practical introduction to Honda ECU chipping: what it means, the essential tools required, and the process of burning new bin files.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference, diagnostics]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'What You Need'
    url: /pgmfi/wiki/library/what-you-need
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# What You Need

"Chipping" an [ECU](/cars/ecu/ecu) means replacing the program running the [ECU](/cars/ecu/ecu). Chipping is just slang. What we actually do is program (or "burn") a new bin file to the [ROM](/cars/rom/rom) to replace the program currently running the [ECU](/cars/ecu/ecu). In order to chip an [ECU](/cars/ecu/ecu), you will need the following:

- [Soldering Iron](/cars/ecu/soldering-iron) - to solder chips in to the [ECU](/cars/ecu/ecu)
- [Desoldering Tool](/cars/ecu/desoldering-tool) - to remove chips/solder from an [ECU](/cars/ecu/ecu). A [Desoldering Iron](/cars/ecu/desoldering-iron), [Desoldering Braid](/cars/wiring/desoldering-braid), or a [Desoldering Station](/cars/ecu/desoldering-station) will also work. Read the [Desoldering Tips](/cars/ecu/desoldering-tips). If you are uncomfortable doing this, or dont have access to the tools, some of the PGMFI members will sell you a [ZIF](/cars/rom/zif)-Socketed [ECU](/cars/ecu/ecu)
- [Rom Editor](/cars/rom/rom-editor) - to create new bin file to burn to the Chip
- [Rom Burner](/cars/ecu/rom-burner) - to a chip to replace the stock program
- [ROM Library](/cars/ecu/ecu-definition-codes) - To get some ready made bins
- [Chips For ECUs](/cars/rom/chips-for-ec-us) - to burn the new Bin file to - [the ATMEL AT29C256](/cars/diagnostics/29c256) seems to be the chip to get
- [Parts For ECUs](/cars/ecu/parts-for-ec-us)- is a fairly comprehensive list of the parts needed for [ECU](/cars/ecu/ecu)s.

Sounds pretty easy `eh`? Dave B. wrote a great [Introduction To ECUChipping](/cars/rom/introduction-to-ecu-chipping) article that is an excellent place to start learning about chipping [ECU](/cars/ecu/ecu)s NOTE: [OBD0 MPFI](/cars/diagnostics/obd0mpfi) [ECU](/cars/ecu/ecu)s do not always have a [ROM](/cars/rom/rom) for you to replace. Don't despair, [Chipping An88-89 ECU](/cars/rom/chipping-an88-89ecu) is possible, too.
