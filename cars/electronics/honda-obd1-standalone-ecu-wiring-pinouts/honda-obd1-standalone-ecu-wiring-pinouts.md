---
title: 'Honda OBD1 (1992-1995) Standalone ECU Wiring & Plug-and-Play Adapter Pinouts'
summary: 'Pinout maps and hardware setup for OBD1 Civic/Integra (P28/P30/P72) factory harnesses: A/B/D connectors, VR sensor inputs, and standalone board assembly.'
tags: [obd1, p28, p30, p72, pinout, pnp-adapter, standalone]
applies_to:
  models: [civic, integra, accord, prelude]
  chassis: [eg, ek, dc2, cb7, bb]
  engines: [d-series, b-series, h-series]
  ecus: [obd1-p28, obd1-p30, obd1-p72]
complexity: intermediate
sources:
  - title: 'Honda OBD1 PnP'
    url: 'https://rusefi.com/forum/viewtopic.php?t=3077'
    adapted: true
    author: AndreyB
  - title: 'Honda OBD1 Setup'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2133'
    adapted: true
    author: blundar
---

# Honda OBD1 (1992-1995) Standalone ECU Wiring & Plug-and-Play Adapter Pinouts

## Overview

1992-1995 Honda OBD1 vehicles (EG Civic, DC2 Integra, CB7 Accord) use a 3-plug ECU interface (Connectors A, B, and D). This reference covers wiring standalone ECUs directly to factory OBD1 Honda harness plugs.

---

## 1. Primary Connector Pinouts (Plugs A, B, D)

### Connector A (26-Pin Main Connector)

| Pin | Function | Sensor / Actuator |
| --- | --- | --- |
| A1 | Fuel Pump Relay Ground | Main Relay Pin 7 |
| A7 | FLR Output | Fuel Injector #1 |
| A8 | FLR Output | Fuel Injector #2 |
| A3 | FLR Output | Fuel Injector #3 |
| A5 | FLR Output | Fuel Injector #4 |
| A25 | Power Ground | Engine Ground Stud |

---

## 2. Plug-and-Play ECU Board Assembly

```carousel
![Frankenso 0.4 Honda OBD1 Adapter Board Top View](topic_939_frankenso_0_4_honda_obd1_top1.jpg)
*Frankenso 0.4 Honda OBD1 plug-and-play adapter board header assembly.*
<!-- slide -->
![Frankenso 0.4 Honda OBD1 Adapter Board Overview](topic_939_frankenso_0_4_honda_obd1_top2.jpg)
*Frankenso 0.4 Honda OBD1 adapter board overview showing header pin soldering.*
```
