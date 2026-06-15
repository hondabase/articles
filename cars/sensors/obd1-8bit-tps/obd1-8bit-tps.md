---
summary: "If x is a 8bit TPS value, then: TPS(''x'') = ((hextodec''x'')/229.5100)''%'' WOT(100%)= 4.5 v = 4.5/5255 = 229.5 by Calvin Baank"
tags: [ecu, reference, sensors]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit TPS'
    url: /pgmfi/wiki/library/obd1-8bit-tps
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 8bit TPS

If x is a 8-bit TPS value, then:

- TPS(''x'') = ((hextodec''x'')/229.5*100)''%''

[WOT](/cars/reference/wot)(100%)= 4.5 v = 4.5/5*255 = 229.5 by Calvin Baank
