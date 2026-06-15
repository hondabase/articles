---
summary: "All Honda ECUs use 5v TTL signaling for serial communication. In order to connect to an ECU, if the hardware used for Data Logging doesn't support this, you must use some form of serial adapter."
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Serial Adapter'
    url: /pgmfi/wiki/library/serial-adapter
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Serial Adapter

All Honda [ECU](/cars/ecu/ecu)s use 5v [TTL](/cars/sensors/ttl) signaling for [serial communication](/cars/tuning/serial-communication). In order to connect to an [ECU](/cars/ecu/ecu), if the hardware used for [Data Logging](/cars/diagnostics/data-logging) doesn't support this, you must use some form of serial adapter. Below are some of the more common adapters available: | **Unit** | **From Interface** | **To Interface** | | :--- | :--- | :--- | | [Super Droid Robots](http://www.superdroidrobots.com/rs232.htm) | RS232 | [TTL](/cars/sensors/ttl) | | [CompSys](http://web.archive.org/web/20241209231224/http://www.compsys1.com/workbench/On_top_of_the_Bench/Max233_Adapter/max233_adapter.html) | RS232 | [TTL](/cars/sensors/ttl) | | [Lucas Schaar]() | RS232 | [TTL](/cars/sensors/ttl) | | [Gigatechnology](http://web.archive.org/web/20190105220149/http://www.gigatechnology.com:80/usbmodprod.html) | USB 1.1 | [TTL](/cars/sensors/ttl) |
