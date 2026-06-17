---
summary: 'CN2 é o conector para a porta série numa ECU OBD1. Aqui está a pinagem do conector de dados NA ECU Honda: 1: GND 2: RX (enviar dados...'
applies_to:
  obd: [1]
  brand: Honda
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
    title: OBD1CN2
    url: /pgmfi/wiki/library/obd1cn2
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1CN2

`CN2` é o conector para a porta série numa [ECU](/cars/ecu/ecu) [OBD1](/cars/wiring/obd1). ![CN2_location.jpg](CN2_location.jpg) Aqui está a pinagem do conector de dados *NA* [ECU](/cars/ecu/ecu) Honda:

- 1: GND
- 2: RX (enviar dados do PC para a [ECU](/cars/ecu/ecu))
- 3: +5 Volt
- 4: TX (enviar dados da [ECU](/cars/ecu/ecu) para o PC)
- 5: N.C. (não conectado)

Esta porta é half-duplex (RX e TX estão conectados) na sua forma original (stock). Consulte [OBD1 J12](/cars/wiring/obd1j12) para mais informações sobre a modificação para full-duplex. Um bom pin header para `CN2` é o componente da digikey part# 640456-4 ***Pergunta de [Web Geek](/cars/electronics/web-geek)*** "Existem 3 resultados de pesquisa para essa referência, qual é a correta?" Para mais informações, consulte este excelente post de Jim Truett: [https://web.archive.org/web/http://forum.pgmfi.org/viewtopic.php?t=1663](/pgmfi/forum/topic.php?id=1663)
