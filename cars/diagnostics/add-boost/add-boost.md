---
summary: 'crome scripts work on p06, p28, p30 (edm, jdm, usdm), p72; it recognizes the rom as do most other Rom editors.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Add Boost'
    url: /pgmfi/wiki/library/add-boost
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Add Boost

crome scripts work on p06, p28, p30 (edm, jdm, usdm), p72; it recognizes the rom as do most other Rom editors. Not all scripts work on all [ROM](/cars/rom/rom)s. Boost is a notable one to mention (works mainly w/ P72 currently). [Crome ROMEditor](/cars/rom/crome-rom-editor)'s "add boost" script enlarges the stock tables so that there is an area for boost. This is very similar to what the boost tab of [Uber Data ERM](/cars/rom/uber-data-erm) does too. The stock table size is changed 10x20 -> 15x20 (edit this if this is not right). The last 5 columns are assigned MAP values in the boost region instead of NA, allowing the [ECU](/cars/ecu/ecu) to understand what to do when the car sees boost (MAP sensor reads a pressure greater than atmospheric pressure).
