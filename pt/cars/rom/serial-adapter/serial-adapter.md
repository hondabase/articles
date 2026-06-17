---
summary: 'Todas as ECUs da Honda utilizam sinalização TTL de 5v para comunicação série. Para ligar a uma ECU, se o hardware utilizado para Data Logging não suportar esta sinalização, deve usar algum tipo de adaptador de série.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Serial Adapter'
    url: /pgmfi/wiki/library/serial-adapter
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adaptador de Série

Todas as [ECU](/cars/ecu/ecu)s da Honda utilizam sinalização [TTL](/cars/sensors/ttl) de 5v para [comunicação série](/cars/tuning/serial-communication). Para se ligar a uma [ECU](/cars/ecu/ecu), se o hardware utilizado para [Data Logging](/cars/diagnostics/data-logging) não suportar esta sinalização, deve usar algum tipo de adaptador de série. Abaixo estão alguns dos adaptadores mais comuns disponíveis: | **Unidade** | **Interface de Origem** | **Interface de Destino** | | :--- | :--- | :--- | | [Super Droid Robots](http://www.superdroidrobots.com/rs232.htm) | RS232 | [TTL](/cars/sensors/ttl) | | [CompSys](http://web.archive.org/web/20241209231224/http://www.compsys1.com/workbench/On_top_of_the_Bench/Max233_Adapter/max233_adapter.html) | RS232 | [TTL](/cars/sensors/ttl) | | [Lucas Schaar]() | RS232 | [TTL](/cars/sensors/ttl) | | [Gigatechnology](http://web.archive.org/web/20190105220149/http://www.gigatechnology.com:80/usbmodprod.html) | USB 1.1 | [TTL](/cars/sensors/ttl) |
