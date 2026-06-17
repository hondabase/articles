---
summary: 'Injetores Peak and Hold, também conhecidos como Injetores de Baixa Impedância. Impedância tipicamente de ~2-5 ohms. A 12 volts, isto representa um consumo de ~6-2,4A.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - wiring
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: 'Peak And Hold Injectors'
    url: /pgmfi/wiki/library/peak-and-hold-injectors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Injetores Peak and Hold

[Injetores Peak and Hold](/cars/wiring/peak-and-hold-injectors), também conhecidos como [Injetores de Baixa Impedância](/cars/fueling/low-impedance-injectors). Impedância tipicamente de ~2-5 ohms. A 12 volts, isto representa um consumo de ~6-2.4 amperes. A corrente elevada fará com que os injetores funcionem mais quentes. A corrente de pico (peak) abre o injetor de forma nítida e decisiva. Em seguida, uma corrente de manutenção (hold) mais baixa mantém o injetor aberto. Para fazer funcionar estes injetores com a ECU Honda, poderá necessitar de utilizar uma [Caixa de Resistências (Resistor Box)](/cars/wiring/resistor-box) em série. O sistema [OBD0](/cars/rom/obd0) já tem uma caixa de resistências instalada. O sistema [OBD1](/cars/wiring/obd1) não possui uma [Caixa de Resistências (Resistor Box)](/cars/wiring/resistor-box). O sistema [OBD2](/cars/wiring/obd2) não possui uma [Caixa de Resistências (Resistor Box)](/cars/wiring/resistor-box).
