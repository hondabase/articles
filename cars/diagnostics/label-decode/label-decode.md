---
summary: 'You can find out a lot from reading the label on a OBD1 ECU. This applies mainly to the Civic ECUs...'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  brand: Acura/Honda
  models: [civic, crx, del-sol, integra]
  chassis: [ef, eg, eg-eh, ek]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Label Decode'
    url: /pgmfi/wiki/library/label-decode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Label Decode

You can find out a lot from reading the label on a [OBD](/cars/wiring/obd)1 [ECU](/cars/ecu/ecu). This applies mainly to the Civic [ECU](/cars/ecu/ecu)s... dunno bount the integra ones. **37820-ABC-XYZ**| **Digits** | **Meaning** | | :--- | :--- | | ABC | Engine [ECU](/cars/ecu/ecu) designed for | | X | Market of [ECU](/cars/ecu/ecu) - see chart below | | Y | 0: 5-speed, 5: Auto | | Z | even number: "11F0" board, odd number: "1720" board | | **Code** | **Market** | | :--- | :--- | | Axx | [USDM](/cars/sensors/usdm) 49-state | | Lxx | [USDM](/cars/sensors/usdm) Cali Emissions | | xxx | [JDM](/cars/sensors/jdm) | | Jxx | [JDM](/cars/sensors/jdm) | | 9xx | [JDM](/cars/sensors/jdm) (auto) | | Gxx | [EDM](/cars/wiring/edm) | | Qxx | [Oz DM](/cars/reference/oz-dm) | | Cxx | Canadian | | Nxx | usually factory reprogrammed, no particular market | Example: **37820-P28-A52**

- P28 = [SOHC](/cars/sensors/sohc) VTEC D16Z6
- A = US, 49 state
- 5 = Auto
- 2 = "11F0" board

| *Library.LabelDecode moved from Library.OBD1LabelDecode on 21 Apr 2004 - 15:31 by Home.blundar* - [put it back](https://web.archive.org/web/http://www.pgmfi.org/twiki/bin/rename/Library/LabelDecode?newweb=Library&newtopic=OBD1LabelDecode&confirm=on "Click to move topic back to previous location, with option to change references.") | | :--- |
