---
summary: 'Autor: George Data: 120302 22:36 O Sensor de Velocidade do Veículo (VSS), guardado na posição de RAM 06Ch, parece de facto ser linear (para minha surpresa!), mas apenas consegue ler até ~157 km/h.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - referencia
  - sensores
  - diagnosticos
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0VSS
    url: /pgmfi/wiki/library/obd0vss
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0VSS

**Autor:** George

**Data:** 12-03-02 22:36

O [Sensor de Velocidade do Veículo](/cars/wiring/vehicle-speed-sensor) ([VSS](/cars/sensors/vss)), guardado na posição de [RAM](/cars/reference/ram) `06Ch` parece de facto ser linear (para minha surpresa!), mas apenas consegue ler até ~157 km/h. Utilizando o Excel, a fórmula é aproximadamente: Velocidade (km/h) = 0.6229x - 2.1385
