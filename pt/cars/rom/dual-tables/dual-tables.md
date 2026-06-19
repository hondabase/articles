---
summary: 'Explicação das estruturas de ROM com tabelas duplas em ECUs Honda, permitindo funcionalidades de afinação avançadas como mapas de combustível e ignição dependentes do VTEC.'
tags: [ecu, reference, tuning, rom, sensors]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Dual Tables'
    url: /pgmfi/wiki/library/dual-tables
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Tabelas Duplas

Tabelas Duplas refere-se simplesmente à existência de dois conjuntos de informação de combustível/ignição (timing) numa única [ROM](/cars/rom/rom). O [VTEC](/cars/sensors/vtec) é um exemplo disso - existe um conjunto de informação de afinação para a [Low Cam](/cars/sensors/low-cam) e outro para a [High Cam](/cars/sensors/high-cam). Adicionalmente, o [ECUNitrous Control](/cars/rom/ecu-nitrous-control) planeia incluir dois conjuntos de informação de afinação para que a [ECU](/cars/ecu/ecu) possa ser afinada para óxido nitroso (nitrous). Veja também: [Dual Roms](/cars/tuning/dual-roms)
