---
summary: 'O EA (EA Prime) é um pino no MCU que controla se o MCU é executado a partir da ROM interna ou de um chip ROM externo.'
applies_to:
  obd: [1]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: EA
    url: /pgmfi/wiki/library/ea
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# EA

_EA (EA Prime) é um pino no [MCU](/cars/rom/mcu) que controla se o [MCU](/cars/rom/mcu) é executado a partir da [ROM Interna](/cars/rom/internal-rom) ou de um chip [ROM](/cars/rom/rom) externo. O pino _EA é o pino 31 nos [MCUs](/cars/rom/mcu) [Intel8051](/cars/rom/intel8051) de 40 pinos. O [J1](/cars/rom/obd1j1) nas [ECUs](/cars/ecu/ecu) [OBD1](/cars/wiring/obd1) controla o estado do _EA, sendo utilizado para ativar uma [ROM](/cars/rom/rom) externa que instale.
