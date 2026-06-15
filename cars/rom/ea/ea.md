---
summary: 'EA (EA Prime) is a pin on the MCU that controls whether the MCU runs off Internal ROM or an external ROM chip.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: EA
    url: /pgmfi/wiki/library/ea
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# EA

_EA (EA Prime) is a pin on the [MCU](/cars/rom/mcu) that controls whether the [MCU](/cars/rom/mcu) runs off [Internal ROM](/cars/rom/internal-rom) or an external [ROM](/cars/rom/rom) chip. _EA is pin 31 on 40-pin [Intel8051](/cars/rom/intel8051) [MCU](/cars/rom/mcu)s [J1 ](/cars/rom/obd1j1) on [OBD1](/cars/wiring/obd1) [ECU](/cars/ecu/ecu)s controls the state of _EA, and is used to activate an external [ROM](/cars/rom/rom) you install.
