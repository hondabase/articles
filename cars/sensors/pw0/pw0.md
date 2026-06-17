---
summary: 'A complete hardware and software reference guide for the JDM and European OBD0 PW0 DOHC VTEC ECU, featuring ROM address calibrations and mapping.'
tags: [ecu, vtec, reference]
applies_to:
  obd: [0]
  models: [civic, crx, del-sol, integra]
  chassis: [da, dc2, ef, eg, eg-eh, ek]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: PW0
    url: /pgmfi/wiki/library/pw0
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Honda PW0 ECU Reference Guide

The PW0 Engine Control Unit (ECU) is a classic OBD0 controller equipped in JDM (Japanese Domestic Market) and European-market Hondas from 1989 to 1991. Sourced from the JDM Civic SiR (EF9), CRX SiR (EF8), and Integra XSi/RSi (DA6), the PW0 controls the first-generation DOHC VTEC 1.6L B16A engine.

## Overview

As one of Honda's earliest VTEC ECUs, the PW0 features a robust internal layout that includes dual knock sensor inputs (JDM versions) and uses an OKI-based microcontroller architecture. Like the similar [PR3 ECU](/cars/sensors/pr3), the PW0 is highly popular among enthusiasts restoring or tuning 4th-generation Civics and CRXs.

This guide lists the critical ROM address locations for modifying parameters (such as checksums, VTEC crossovers, and rev limits) on both JDM and European-spec PW0 ROMs.

### ECU Board Scans & Hardware

For hardware repairs or socketing verification, refer to these board scans:
- [PW0 Component View 1](PW0-000_component1.jpeg)
- [PW0 Component View 2](PW0-000_component2.jpeg)
- [PW0 Knock Sensor Circuitry](PW0-000_knock.jpeg)
- [PW0 Solder Joints (Back View)](PW0-E00_solder.jpeg)

---

## JDM PW0 ROM Address Map

Below are the hex address offsets within the EEPROM for JDM PW0 calibrations (e.g., standard PW0-000 ROMs):

| Location | Bytes | Description | Notes |
| :--- | :---: | :--- | :--- |
| **20B2** | 1 | Checksum Bypass | Change from `0xC9` (perform checksum) to `0xCB` (bypass checksum) to prevent solid CEL on modified ROMs |
| **391A** | 1 | High Cam Rev Limiter | Warm/VTEC engine RPM fuel cut (uses OBD0 8-bit RPM formula) |
| **391C** | 1 | Low Cam Rev Limiter | Low cam engine RPM fuel cut (uses OBD0 8-bit RPM formula) |
| **3922** | 1 | High Cam Rev Recovery | RPM where VTEC fuel cut recovers |
| **3AD8** | 1 | VTEC Disengage Speed | Lower VTEC cut-off speed threshold (uses OBD0 VTEC formula) |
| **3AD9** | 1 | VTEC Engage Speed | VTEC engagement speed threshold |
| **3ADA** | 1 | VTEC Disengage RPM | Crossover low RPM hysteresis limit (3AD8 is typically active) |
| **3ADB** | 1 | VTEC Engage RPM | Crossover high RPM activation point (3AD9 is typically active) |
| **3BE6** | 255 | Low Cam Ignition Map | 15x17 low cam ignition advance map (uses OBD0 Ignition formula) |
| **3CE5** | 255 | High Cam Ignition Map | 15x17 VTEC ignition advance map (first row is typically empty filler) |
| **3DE4** | 255 | Low Cam Fuel Table | 15x17 base fueling lookup map (uses OBD0 Fuel formula) |
| **3EE3** | 15 | Low Cam Multipliers | Column multiplier coefficients for fuel map 1 |
| **3EF2** | 255 | High Cam Fuel Table | 15x17 VTEC fueling lookup map (uses OBD0 Fuel formula) |
| **3FF1** | 15 | High Cam Multipliers | Column multiplier coefficients for VTEC fuel map |

---

## European PW0 ROM Address Map

Below are the hex address offsets within the EEPROM for European-spec PW0 calibrations:

| Location | Bytes | Description | Notes |
| :--- | :---: | :--- | :--- |
| **1F21** | 1 | Checksum Bypass | Change from `0xC9` to `0xCB` to bypass checksum checks |
| **3928** | 1 | High Cam Rev Limiter | Warm/VTEC engine RPM fuel cut (uses OBD0 8-bit RPM formula) |
| **392A** | 1 | Low Cam Rev Limiter | Low cam engine RPM fuel cut (uses OBD0 8-bit RPM formula) |
| **3930** | 1 | High Cam Rev Recovery | RPM where VTEC fuel cut recovers |
| **3AEC** | 1 | VTEC Disengage Speed | Lower VTEC cut-off speed threshold (3AEC is typically active) |
| **3AED** | 1 | VTEC Engage Speed | VTEC engagement speed threshold (3AED is typically active) |
| **3AEE** | 1 | VTEC Disengage RPM | Crossover low RPM hysteresis limit |
| **3AEF** | 1 | VTEC Engage RPM | Crossover high RPM activation point |
| **3BE6** | 255 | Low Cam Ignition Map | 15x17 low cam ignition advance map |
| **3CE5** | 255 | High Cam Ignition Map | 15x17 VTEC ignition advance map |
| **3DE4** | 255 | Low Cam Fuel Table | 15x17 base fueling lookup map |
| **3EE3** | 15 | Low Cam Multipliers | Column multiplier coefficients for fuel map 1 |
| **3EF2** | 255 | High Cam Fuel Table | 15x17 VTEC fueling lookup map |
| **3FF1** | 15 | High Cam Multipliers | Column multiplier coefficients for VTEC fuel map |

---

## Fuel Column Multiplier Formula

Because 8-bit cell values (scaled `0x00` to `0xFF` or `0-255`) cannot cover a wide enough pulse-width range without losing resolution, the PW0 ECU applies a column-specific multiplier coefficient to `each` load column:

$$\text{Column Multiplier} = \frac{2^{\text{Multiplier Value}}}{4}$$

The final calculated injector pulse-width value uses this multiplier to scale the raw fuel map cell value into the final injection duration commanded by the ECU. Refer to the [understanding maps guide](/cars/fueling/understanding-maps) for a step-by-step example of load scaling.
