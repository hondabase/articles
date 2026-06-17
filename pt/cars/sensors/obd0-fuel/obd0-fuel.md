---
summary: 'Fórmula de combustível OBD0: a = 2 ^ Column Multiplier largura de pulso em ms = (Dec At Addy + (224/a))/(208/a)'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Fuel'
    url: /pgmfi/wiki/library/obd0-fuel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Combustível OBD0

Fórmula de combustível [OBD](/cars/wiring/obd)0:
- a = 2 ^ [Column Multiplier](/cars/rom/column-multiplier)
- largura de pulso (pulsewidth) em ms = ([Dec At Addy](/cars/rom/dec-at-addy) + (224/a))/(208/a)
