---
summary: 'O código de origem divide a leitura do sensor MAP por dois. Isto limita a pressão máxima a que a ECU pode responder a metade do máximo que o sensor MAP é capaz de ler.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - referência
  - tuning
  - rom
  - sensores
  - diagnósticos
sources:
  - name: 'pgmfi.org wiki'
    title: uncorked
    url: /pgmfi/wiki/library/uncorked
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# uncorked

O código de origem divide a leitura do [sensor MAP](/cars/fueling/map-sensor) por dois. Isto limita a pressão máxima a que a [ECU](/cars/ecu/ecu) pode responder a metade do máximo que o [sensor MAP](/cars/fueling/map-sensor) é capaz de ler. Ao remover simplesmente esta divisão, desobstruímos ("uncorked") o [sensor MAP](/cars/fueling/map-sensor) para ler até 11psi de boost.
