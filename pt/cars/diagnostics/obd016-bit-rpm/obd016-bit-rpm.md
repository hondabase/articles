---
summary: 'Fórmula de conversão de RPM para valor hexadecimal de 16 bits para ECUs Honda OBD0.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD016 Bit RPM'
    url: /pgmfi/wiki/library/obd016-bit-rpm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Fórmula de RPM de 16 Bits do OBD0

Para traduzir a rotação do motor (RPM) para os valores hexadecimais de 16 bits esperados pelas ECUs Honda OBD0:

`Valor Hex da ECU = 1920000 / RPM`

### Conversão no Excel

Se estiver a compilar tabelas de ROM personalizadas no Microsoft Excel ou Google Sheets, pode calcular a string hexadecimal usando:

`=DEC2HEX(1920000 / RPM_value)`
