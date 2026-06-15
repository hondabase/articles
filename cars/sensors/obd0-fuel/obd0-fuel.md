---
summary: 'OBD0 fuel formula: a = 2 ^ Column Multiplier pulsewidth in ms = (Dec At Addy + (224/a))/(208/a)'
tags: [ecu, reference, sensors]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Fuel'
    url: /pgmfi/wiki/library/obd0-fuel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Fuel

[OBD](/cars/wiring/obd)0 fuel formula: - a = 2 ^ [Column Multiplier](/cars/rom/column-multiplier)
- pulsewidth in ms = ([Dec At Addy](/cars/rom/dec-at-addy) + (224/a))/(208/a)
