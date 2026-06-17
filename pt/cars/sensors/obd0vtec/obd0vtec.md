---
summary: 'Fórmula de conversão de RPM para os valores de ativação do VTEC em OBD0 e OBD1.'
applies_to:
  obd: [0, 1]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0VTEC
    url: /pgmfi/wiki/library/obd0vtec
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Fórmula de RPM do VTEC OBD0 e OBD1

Nas ECUs Honda VTEC OBD0 e OBD1, os limites de ativação (engagement) e desativação do VTEC são determinados utilizando a seguinte fórmula:

`RPM = (Valor_Decimal - 128) * 62.52`

Onde:

* `Valor_Decimal` é o valor na base 10 (decimal) do byte localizado nos endereços de ativação/desativação de RPM do VTEC na ROM.
