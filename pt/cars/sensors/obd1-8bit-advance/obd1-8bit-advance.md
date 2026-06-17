---
summary: 'Fórmula de conversão do avanço do ponto de ignição para ECUs Honda OBD1 de 8 bits.'
applies_to:
  obd: [1]
complexity: beginner
tags:
  - ecu
  - referência
  - sensores
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit Advance'
    url: /pgmfi/wiki/library/obd1-8bit-advance
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Fórmula de Avanço de Ignição de 8 Bits OBD1

Nas ECUs Honda OBD1 de 8 bits, o valor do avanço de ignição (em graus) é calculado a partir do valor em byte `v` da tabela raw utilizando a seguinte fórmula:

`Avanço de Ignição (Graus) = (v - 24) / 4`

Onde:
*   `v` é a representação decimal do byte na célula do mapa de ignição.
