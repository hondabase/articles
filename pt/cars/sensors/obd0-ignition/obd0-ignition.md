---
summary: 'Fórmula de conversão do ponto de ignição para ECUs Honda OBD0.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - referência
  - sensores
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ignição OBD0'
    url: /pgmfi/wiki/library/obd0-ignition
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Fórmula de Ignição OBD0

Nas ECUs Honda OBD0, o valor em byte bruto armazenado na ROM é convertido em graus de avanço de ignição usando a seguinte fórmula:

`Avanço de Ignição (Graus) = (Valor_Decimal - 15) * 0.36`

Onde:

* `Valor_Decimal` é o valor em base 10 do byte localizado no offset do mapa de ignição (frequentemente referido como o valor no endereço).
