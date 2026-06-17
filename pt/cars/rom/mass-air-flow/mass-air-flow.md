---
summary: 'Um sistema de gestão de motor por fluxo de massa de ar utiliza um sensor de fluxo de massa de ar (Maf Sensor) posicionado na admissão para medir diretamente a massa de ar que entra no motor.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Mass Air Flow'
    url: /pgmfi/wiki/library/mass-air-flow
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mass Air Flow

Um sistema de gestão de motor por Mass Air Flow (fluxo de massa de ar) utiliza um sensor de fluxo de massa de ar ([Maf Sensor](/cars/wiring/maf-sensor)) posicionado no coletor ou conduta de admissão para medir diretamente a massa de ar que entra no motor. Com esta informação e o tamanho dos injetores, a [ECU](/cars/ecu/ecu) consegue calcular a largura de pulso do injetor de combustível necessária para fornecer a relação ar-combustível ([Air Fuel Ratio](/cars/fueling/air-fuel-ratio)) pretendida. Os sistemas MAF utilizam tipicamente tabelas de valores alvo de [Air Fuel Ratio](/cars/fueling/air-fuel-ratio) em função do fluxo de ar. Isto difere dos sistemas [Speed Density](/cars/diagnostics/speed-density) (como os utilizados nos sistemas Honda PGM-FI), que utilizam tabelas de eficiência volumétrica ([Volumetric Efficiency](/cars/rom/volumetric-efficiency)) combinadas com medições de sensores para estimar o fluxo de ar sem o medir diretamente.
