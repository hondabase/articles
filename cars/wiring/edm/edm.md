---
summary: 'Reference for EDM (European Domestic Market) Honda ECUs, detailing common hardware differences such as the lack of an injector test circuit.'
tags: [ecu, reference, sensors, wiring, conversion, diagnostics]
applies_to:
  brand: Acura/Honda
  models: [civic, integra]
  chassis: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: EDM
    url: /pgmfi/wiki/library/edm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# EDM

European Domestic Market (EDM) refers to Honda vehicles produced specifically for the European market.

**Compare to:** [JDM](/cars/sensors/jdm), [USDM](/cars/sensors/usdm)

### OBD1 Hardware Differences

[EDM](/cars/wiring/edm) [OBD1 Civic Integra](/cars/sensors/obd1-civic-integra) [ECU](/cars/ecu/ecu)s generally lack several sensors and circuits commonly found in [USDM](/cars/sensors/usdm) models:

*   [Injector Test Circuit](/cars/diagnostics/injector-test-circuit)
*   [Knock Sensor](/cars/ignition/knock-sensor)

*   [Electrical Load Detector](/cars/sensors/electrical-load-detector)
*   [Pressure Atmosphere](/cars/rom/pressure-atmosphere) sensors

They typically resemble [USDM](/cars/sensors/usdm) [ECU](/cars/ecu/ecu)s but with fewer populated components on the circuit board.

### OBD2 and Beyond

After 1996, [EDM](/cars/wiring/edm) Hondas utilize the [OBD](/cars/wiring/obd)2 family of [ECU](/cars/ecu/ecu)s; however, they are not OBDII diagnostic compliant. These units feature only a 3-wire [DLC](/cars/wiring/dlc) and communicate exclusively with PGM testers.

EOBD (European On-Board Diagnostics) is the next generation of diagnostics. All petrol-powered road cars and light trucks manufactured after Model Year 2000 must comply with this standard.
