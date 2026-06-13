---
summary: 'crome scripts work on p06, p28, p30 (edm, jdm, usdm), p72; it recognizes the rom as do most other Rom editors.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# Add Boost

crome scripts work on p06, p28, p30 (edm, jdm, usdm), p72; it recognizes the rom as do most other Rom editors. Not all scripts work on all [ROM](/cars/electronics/rom)s. Boost is a notable one to mention (works mainly w/ P72 currently). [Crome ROMEditor](/cars/electronics/crome-rom-editor)'s "add boost" script enlarges the stock tables so that there is an area for boost. This is very similar to what the boost tab of [Uber Data ERM](/cars/electronics/uber-data-erm) does too. The stock table size is changed 10x20 -> 15x20 (edit this if this is not right). The last 5 columns are assigned MAP values in the boost region instead of NA, allowing the [ECU](/cars/electronics/ecu) to understand what to do when the car sees boost (MAP sensor reads a pressure greater than atmospheric pressure).
