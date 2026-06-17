---
summary: 'Os emuladores de ROM (ROM Emulators) "parecem" uma ROM para qualquer dispositivo a que os ligue. Na maioria dos casos aqui, isso seria normalmente uma ECU.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rom Emulator'
    url: /pgmfi/wiki/library/rom-emulator
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ROM Emulator

Os emuladores de [ROM](/cars/rom/rom) "parecem" uma [ROM](/cars/rom/rom) para qualquer dispositivo a que os ligue. Na maioria dos casos aqui, isso seria normalmente uma [ECU](/cars/ecu/ecu). A característica mais importante de um emulador de ROM ([Rom Emulator](/cars/rom/rom-emulator)) em comparação com uma [EPROM](/cars/rom/eprom) ou mesmo uma [FLASH](/cars/rom/flash)-[ROM](/cars/rom/rom) é que se pode alterar os dados que o emulador de ROM contém no momento (on the fly), enquanto este está a funcionar. Na maioria das vezes, isto é conseguido utilizando [SRAM](/cars/sensors/sram)/NVSRAM associada a um conjunto de portas lógicas ou a um FPGA para evitar o processamento lento de dados. O [Xtronics Romulator](http://web.archive.org/web/20260528071037/https://xtronics.com/) é o emulador de ROM ([Rom Emulator](/cars/rom/rom-emulator)) mais comummente falado, uma vez que é recomendado pela [Hon Data](/cars/diagnostics/hon-data) para utilização com os seus produtos.
