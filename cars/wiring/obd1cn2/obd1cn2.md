---
summary: "CN2 is the connector to the serial port on an OBD1 ECU. !CN2location.jpgHere's the pinout of the Dataconnector IN a Honda ECU: 1: GND 2: RX (send Data..."
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [1]
  brand: Honda
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: OBD1CN2
    url: /pgmfi/wiki/library/obd1cn2
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1CN2

`CN2` is the connector to the serial port on an [OBD1](/cars/wiring/obd1) [ECU](/cars/ecu/ecu). ![CN2_location.jpg](CN2_location.jpg)Here's the pinout of the Dataconnector *IN* a Honda [ECU](/cars/ecu/ecu):

- 1: GND
- 2: RX (send Data from the PC to the [ECU](/cars/ecu/ecu))
- 3: +5 Volt
- 4: TX (send Data from [ECU](/cars/ecu/ecu) to the PC)
- 5: N.C. (not connected)

This port is half-duplex (RX and TX are connected) in stock form. See [OBD1 J12](/cars/wiring/obd1j12) for more information about full-duplex modification. A good pin header for `CN2` is digikey part# 640456-4 ***Question From [Web Geek](/cars/electronics/web-geek)_*** "There are 3 search results for that part #, which is the right one?" For more information see this excellent post by Jim Truett: [https://web.archive.org/web/http://forum.pgmfi.org/viewtopic.php?t=1663](/pgmfi/forum/topic.php?id=1663)
