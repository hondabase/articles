---
summary: "CN2 is the connector to the serial port on an OBD1 ECU. !CN2location.jpgHere's the pinout of the Dataconnector IN a Honda ECU: 1: GND 2: RX (send Data..."
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
---

# OBD1CN2

CN2 is the connector to the serial port on an [OBD1](/cars/electronics/obd1) [ECU](/cars/electronics/ecu). ![CN2_location.jpg](CN2_location.jpg)Here's the pinout of the Dataconnector *IN* a Honda [ECU](/cars/electronics/ecu):

- 1: GND
- 2: RX (send Data from the PC to the [ECU](/cars/electronics/ecu))
- 3: +5 Volt
- 4: TX (send Data from [ECU](/cars/electronics/ecu) to the PC)
- 5: N.C. (not connected)

This port is half-duplex (RX and TX are connected) in stock form. See [OBD1 J12](/cars/electronics/obd1j12) for more information about full-duplex modification. A good pin header for CN2 is digikey part# 640456-4 ***Question From [Web Geek](/cars/electronics/web-geek)_*** "There are 3 search results for that part #, which is the right one?" For more information see this excellent post by Jim Truett: [http://forum.pgmfi.org/viewtopic.php?t=1663](/pgmfi/forum/topic.php?id=1663)| **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [CN2\\_location.jpg](/pgmfi/wiki/media/library/OBD1CN2/CN2_location.jpg) | mod | 13759 | 14 Apr 2004 - 00:19 | tungsten2k | [OBD](/cars/electronics/obd)1 CN2 Location |
