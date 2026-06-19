---
summary: 'Fórmula de limite de rotação de 8 bits e rotação de reinício do motor para ECUs Honda OBD0 VTEC.'
tags: [ecu, referência, sensores]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD08 Bit Rev'
    url: /pgmfi/wiki/library/obd08-bit-rev
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Fórmula de Limite de Rotação de 8 Bits OBD0

Para as ECUs Honda OBD0 VTEC, os limites de rotação (rev limit) e as rotações de recuperação/reinício são calculados utilizando a seguinte fórmula de 8 bits:

`RPM = 1848000 / Valor_Decimal`

Onde:
* `Valor_Decimal` é o valor em base 10 do byte no endereço do limite de rotação.
