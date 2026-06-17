---
summary: 'Na sua configuração de fábrica, um carro OBD1 possui um conetor de diagnóstico sob o tablier que está ligado à porta de série da ECU.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - hardware
  - educação
  - ecu
  - tuning
  - rom
  - sensores
  - referência
  - cablagem
  - conversão
  - diagnóstico
sources:
  - name: 'pgmfi.org wiki'
    title: OBD1J12
    url: /pgmfi/wiki/library/obd1j12
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1J12

Na sua configuração de fábrica, um carro [OBD1](/cars/wiring/obd1) possui um conetor de diagnóstico sob o tablier que está ligado à porta de série da [ECU](/cars/ecu/ecu). A porta de série da [ECU](/cars/ecu/ecu) também está ligada ao conetor [CN2](/cars/wiring/obd1cn2). Este conetor de diagnóstico funciona em half-duplex, o que significa que existe apenas um fio que é utilizado para receção e transmissão tanto pela ferramenta de diagnóstico como pela [ECU](/cars/ecu/ecu) e, portanto, apenas um dispositivo pode transmitir de cada vez.

O `J12`, quando removido, desliga a linha de receção da linha de transmissão, permitindo que a porta de série funcione em modo full-duplex. Isto significa que ambos os dispositivos podem enviar dados um ao outro em simultâneo através de [CN2](/cars/wiring/obd1cn2). Isto, claro, desativa o conetor de diagnóstico de fábrica sob o tablier. No entanto, o benefício do modo full-duplex é um registo de dados ([Data Logging](/cars/diagnostics/data-logging)) mais fiável. Existe trabalho de programação em curso para tirar partido disto para registar dados a uma taxa de amostragem muito superior, sem corromper ou colidir com quaisquer comandos enviados para a [ECU](/cars/ecu/ecu).

Numa [ECU](/cars/ecu/ecu) [JDM](/cars/sensors/jdm) P30 (quadrada pequena), este jumper é o `J4`.

Imagem do `J12` OBD1: (12/04/03 - Lego Z)
 ![j12.jpg](j12.jpg)
