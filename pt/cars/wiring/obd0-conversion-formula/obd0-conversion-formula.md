---
summary: 'Descreva a Fórmula de Conversão OBD0 aqui. O RPM de 16 bits OBD0 é utilizado para limitadores de rotação, ralenti alvo (target idle) e para a maioria dos outros valores de RPM de 16 bits na ROM.'
applies_to:
  obd: [0]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Conversion Formula'
    url: /pgmfi/wiki/library/obd0-conversion-formula
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Fórmula de Conversão OBD0

Descreva a [Fórmula de Conversão OBD0](/cars/wiring/obd0-conversion-formula) aqui.

- O [OBD016 Bit RPM](/cars/diagnostics/obd016-bit-rpm) é utilizado para limitadores de rotação, ralenti alvo e a maioria dos outros valores de [RPM](/cars/sensors/rpm) de 16 bits na [ROM](/cars/rom/rom).
- O [OBD0 VSS](/cars/diagnostics/obd0vss) é utilizado para converter os valores na ram `06Ch` para a Velocidade do Veículo.
- O [OBD0 Fuel](/cars/sensors/obd0-fuel) é utilizado para converter os valores hexadecimais nos mapas de combustível em largura de pulso em milissegundos.
- O [OBD0 Ignition](/cars/sensors/obd0-ignition) é utilizado para converter os valores hexadecimais nos mapas de ignição em graus de avanço.
- O [OBD0 VTEC](/cars/sensors/obd0vtec) é utilizado para os valores de VTEC.
- O [OBD08 Bit Rev](/cars/sensors/obd08-bit-rev) é utilizado para os limites de rotação das [ECU](/cars/ecu/ecu)s VTEC [OBD0](/cars/rom/obd0).
