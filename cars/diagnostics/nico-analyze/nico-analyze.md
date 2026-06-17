---
summary: 'Author: XDEep first thanks to nico for a great tool. the mishap im talking about is when you drag the scrollbar up and down, the cells get pushed around.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference, diagnostics]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [civic, crx, del-sol]
  chassis: [ef, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Nico Analyze'
    url: /pgmfi/wiki/library/nico-analyze
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Nico Analyze

**Author:** XDEep first thanks to nico for a great tool. the mishap im talking about is when you drag the scrollbar up and down, the cells get pushed around. so even though i found where the maps where, i had a hard time distinguishing what was what all day until just now i lined up the fuel multipliers into a single row and all the tables magically appeared before me! or just go straight to the beginning of the maps if you know it already. so dont drag, just use the arrow buttons. as an alternative to dragging, you can change the step to 255 to skip a table at a time. change it back to 1 if your cells get pushed and you need to line it up again. precision 1 is the decimal equivalent of the hex value in 8bit form. the default is precision:2 which is the 16bit decimal value of the hex value, which makes it harder to identify the tables at first. thanks to joseph for getting me in the right direction. in this post he explained how to use the program itself-

---

Re: P30 Excel Map Calculator

**Author:** Joseph

Davis

**Date:** 11-12-02 22:00

Sammy, all it is doing is displaying the hex or binary values in decimal. Open a [ROM](/cars/rom/rom) that you have table locations for in the program. Offset is the memory location you're looking for, that the table begins at. Colonnes is how many columns - kinda critical for newbie map recognition. Maps are 15X17 for [OBD](/cars/wiring/obd)0 and 10X20 for [OBD](/cars/wiring/obd)1 - that means Columns X Rows. Set to 15 if [OBD](/cars/wiring/obd)0 and 10 if [OBD](/cars/wiring/obd)1. Step is how many locations the program jumps when you press the up/down arrows on offset (great for searching for a table in a new [ROM](/cars/rom/rom)). Precision is just a multiplier. If you set it to 1 you'll get the real values from 0-255 in decimal instead of 00-FF in hex - since we learn decimal in school it is easier to work with at first. If you sit down with a PM6.bin and the CRX map calculator.xls you'll have zero problems identifying the maps, and the map calculator will have the same decimal as what you see in the Analyser.exe. The P30 kids came up with a similar Excel spreadsheet if you'd rather start there. You see how the values distibute themselves logically across the ignition map? The fuel is doing the same, but the further across the columns you go you have to start using that column's multiplier at the bottom of the map or else it looks like the map starts lean, goes rich, then starts lean + goes rich a couple times across it.
