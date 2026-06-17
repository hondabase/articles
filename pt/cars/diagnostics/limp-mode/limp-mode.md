---
summary: 'Também conhecido como "Limp Home Mode", o Limp Mode é o modo de funcionamento quando a luz de verificação do motor (CEL) da ECU fica acesa fixamente, indicando uma avaria grave.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Limp Mode'
    url: /pgmfi/wiki/library/limp-mode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Limp Mode

Também conhecido como "Limp Home Mode" (Modo de Segurança), o [Limp Mode](/cars/diagnostics/limp-mode) é o modo de funcionamento quando a luz [CEL](/cars/wiring/cel) da [ECU](/cars/ecu/ecu) fica acesa de forma fixa, indicando uma avaria grave. Destina-se a permitir levar o carro para casa, e fará com que o carro funcione com um desempenho muito fraco. O processador de segurança (backup processor) controla o motor sem utilizar a [ROM](/cars/rom/rom) nesta fase. Apenas o sensor TDC e o [Sensor TPS](/cars/diagnostics/tps-sensor) são utilizados neste modo. O limitador de rotação surge às 3500 rpm. Mais informações:

- [OBD0 BACKUP](/cars/diagnostics/obd0backup)

NOTA: Seria útil ter uma lista de quais sensores ativam/não ativam o [Limp Mode](/cars/diagnostics/limp-mode)
