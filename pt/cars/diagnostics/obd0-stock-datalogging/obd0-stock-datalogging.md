---
summary: 'O código de interrupção de série na ECU de fábrica é muito simples. É enviado um endereço hexadecimal de 1 byte para a ECU, e esta responde com o conteúdo da memória RAM nesse endereço.'
applies_to:
  obd: [0]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Stock Datalogging'
    url: /pgmfi/wiki/library/obd0-stock-datalogging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Stock Datalogging

O código de interrupção de série na [ECU](/cars/ecu/ecu) de fábrica é muito simples. É enviado um endereço hexadecimal de 1 byte para a [ECU](/cars/ecu/ecu), e a [ECU](/cars/ecu/ecu) responde com o conteúdo da memória [RAM](/cars/reference/ram) nesse endereço. O motivo pelo qual o código da [ECU](/cars/ecu/ecu) de fábrica não é adequado para datalogging na maioria das circunstâncias é que a porta de série é inicializada a uma taxa de transmissão (baud rate) muito alta. Funciona a (CLK / 64 baud), ou 12Mhz / 64 (187 500 baud), o que não é muito compatível com portas de série comuns. Consulte os tutoriais do [Intel8051](/cars/rom/intel8051) para obter informações sobre isto. Para efetuar datalogging atualmente, o Timer2, que não é utilizado em nenhuma outra parte do código, é usado para inicializar a porta de série a uma velocidade próxima de 9600 baud, com a qual as portas de série dos PCs conseguem comunicar.
