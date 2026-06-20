---
summary: 'Autor: HRED Data: 01/03/03 17:27 Pode alterar o ralenti alvo: procure pelo valor "09c4" que encontra, por exemplo, em PM7FOR6121502.'
tags: [ecu, reference, tuning, sensors]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: '91PM7 Target Idle'
    url: /pgmfi/wiki/library/91pm7-target-idle
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ralenti Alvo da 91PM7

**Autor:** HRED

**Data:** 01-03-03 17:27

Pode alterar o ralenti alvo: procure pelo valor "09c4" que encontra, por exemplo, na ROM PM7FOR6_12-15-02.BIN, uma string com 6 valores de rotação (RPM) como esta: 0A08 09C4 0964 0A77 09C4 0964 substitua todos os valores por este para obter um ralenti alvo de 1000 rpm: 0753 0753 0753 0753 0753 0753 todos os valores utilizam a fórmula [OBD016 Bit RPM](/cars/diagnostics/obd016-bit-rpm). Nicolas HRED França Bordéus
