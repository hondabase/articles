---
summary: 'You can find out a lot from reading the label on a OBD1 ECU. This applies mainly to the Civic ECUs...'
applies_to:
  obd: [1]
  brand: Acura/Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# Label Decode

You can find out a lot from reading the label on a [OBD](/cars/electronics/obd)1 [ECU](/cars/electronics/ecu). This applies mainly to the Civic [ECU](/cars/electronics/ecu)s... dunno bount the integra ones. **37820-ABC-XYZ**| **Digits** | **Meaning** | | :--- | :--- | | ABC | Engine [ECU](/cars/electronics/ecu) designed for | | X | Market of [ECU](/cars/electronics/ecu) - see chart below | | Y | 0: 5-speed, 5: Auto | | Z | even number: "11F0" board, odd number: "1720" board | | **Code** | **Market** | | :--- | :--- | | Axx | [USDM](/cars/electronics/usdm) 49-state | | Lxx | [USDM](/cars/electronics/usdm) Cali Emissions | | xxx | [JDM](/cars/electronics/jdm) | | Jxx | [JDM](/cars/electronics/jdm) | | 9xx | [JDM](/cars/electronics/jdm) (auto) | | Gxx | [EDM](/cars/electronics/edm) | | Qxx | [Oz DM](/cars/electronics/oz-dm) | | Cxx | Canadian | | Nxx | usually factory reprogrammed, no particular market | Example: **37820-P28-A52**

- P28 = [SOHC](/cars/electronics/sohc) VTEC D16Z6
- A = US, 49 state
- 5 = Auto
- 2 = "11F0" board

| *Library.LabelDecode moved from Library.OBD1LabelDecode on 21 Apr 2004 - 15:31 by Home.blundar* - [put it back](http://www.pgmfi.org/twiki/bin/rename/Library/LabelDecode?newweb=Library&newtopic=OBD1LabelDecode&confirm=on "Click to move topic back to previous location, with option to change references.") | | :--- |
