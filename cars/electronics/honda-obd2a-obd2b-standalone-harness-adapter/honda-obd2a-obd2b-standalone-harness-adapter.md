---
title: 'Honda OBD2A & OBD2B (1996-2001) Standalone Adapter & Harness Integration'
summary: 'Comparison between OBD2A (1996-1998) and OBD2B (1999-2001) ECU plug layouts, adapter wiring setups, immobilizer bypass, and standalone installation.'
tags: [obd2a, obd2b, harness-adapter, proteus, hellen, immobilizer, rev-limit]
applies_to:
  models: [civic, integra, cr-v]
  chassis: [ek, dc2, rd1]
  engines: [d-series, b-series]
complexity: intermediate
sources:
  - title: 'Proteus Honda OBD2A adapter'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2175'
    adapted: true
    author: AndreyB
  - title: 'Honda B series Obd2a Wiring and RevLimit'
    url: 'https://rusefi.com/forum/viewtopic.php?t=3034'
    adapted: true
    author: Koullisgg
  - title: 'Honda OBD2 connector'
    url: 'https://rusefi.com/forum/viewtopic.php?t=1461'
    adapted: true
    author: mobyfab
---

# Honda OBD2A & OBD2B (1996-2001) Standalone Adapter & Harness Integration

## Overview

Between 1996 and 2001, Honda transitioned through two distinct wiring standards across EK Civics, DC2 Integras, Prelude BB6s, and RD1 CR-Vs: **OBD2A** (1996–1998) and **OBD2B** (1999–2001). This guide covers harness pinout differences, adapter installation, and immobilizer handling when fitting standalone ECUs.

---

## 1. Key Differences Between OBD2A and OBD2B

| Feature | OBD2A (1996-1998) | OBD2B (1999-2001) |
| --- | --- | --- |
| **ECU Plug Count** | 4 Plugs (A, B, C, D) | 3 Plugs (A, B, C) |
| **Plugs at ECU** | Plugs A, B, C connect to engine | Plugs A and B connect to engine |
| **Body Harness Plug** | Plug D connects to cabin dash | Plug C connects to cabin dash |
| **Immobilizer** | External module (most US models optional) | Integrated internal ECU board |

---

## 2. Standalone Adapter Wiring & Pin Map

When connecting a standalone ECU via adapter harnesses (e.g. Proteus or Hellen adapters):

### Power & Ignition Key Pins

- **OBD2A:** +12V Switched Power at `A11` and `A24`.
- **OBD2B:** +12V Switched Power at `A11` and `A8`.

### Distributor Trigger Lines

- **CKP Sensor (+):** OBD2A `C2` / OBD2B `C8`
- **TDC Sensor (+):** OBD2A `C3` / OBD2B `C9`
- **CYP Sensor (+):** OBD2A `C4` / OBD2B `C10`

---

## 3. Immobilizer Bypass Procedure

Factory OBD2B ECUs (and late European OBD2A ECUs) contain an integrated immobilizer board that inhibits fuel pump relay operation unless an authorized transponder key is detected.

> \[!TIP\] When installing a standalone ECU, the factory immobilizer board is completely bypassed. The standalone ECU directly drives the Main Relay fuel pump line (OBD2A `A16` / OBD2B `A15`), allowing immediate starting without key recoding.
