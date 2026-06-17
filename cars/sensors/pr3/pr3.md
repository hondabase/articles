---
summary: 'Hardware and software reference guide for the OBD0 and OBD1 PR3 DOHC VTEC ECU used in B16A-equipped Integra and Civic models.'
tags: [ecu, vtec, reference]
applies_to:
  obd: [0, 1]
  models: [civic, crx, del-sol, integra]
  chassis: [da, dc2, ef, eg, eg-eh, ek]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: PR3
    url: /pgmfi/wiki/library/pr3
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Honda PR3 ECU Reference Guide

The PR3 Engine Control Unit (ECU) is a prominent Honda controller equipped in B16A DOHC VTEC vehicles between 1989 and 1993. 

> [!IMPORTANT]
> There are two completely different generations of ECUs designated as **PR3** (OBD0 and OBD1). They feature entirely different physical hardware casings, microprocessors, and wiring pinouts, and are **not compatible** in any way.

---

## OBD0 vs. OBD1 PR3 Identification

### OBD0 PR3 (1989–1991)

- **Application:** Sourced from first-generation JDM B16A models (Civic EF9, CRX EF8, Integra DA6).
- **Hardware:** Features the OKI M66x301 microcontroller and dual knock sensor board. Uses the same code structure as the [PW0 ECU](/cars/sensors/pw0).
- **Auto/Manual Jumper:** Check the board layout for transmission jumper identification:
 [OBD0 PR3 Auto/Manual Jumper Identification Scan](OBD0_pr3-auto-manual.jpg)

### OBD1 PR3 (1992–1993)

- **Application:** Sourced from 1992–1993 JDM Integra RSi and XSi models (second-generation B16A).
- **Hardware:** Built on the same standardized motherboard as the [P28](/cars/sensors/p28) and [P30](/cars/sensors/p30) ECUs (typically circuit board part number `02D01720-1500`).
- **Layout Scan:** [OBD1 PR3 Board Layout Scan](https://web.archive.org/web/http://pgmfi.org/resources/FAQ/scans/PR3-OBD1.jpg)

---

## OBD0 PR3 ROM Address Map

Below are the hex address offsets within the 28-pin EEPROM chip for the OBD0 version of the PR3 ECU:

| Location | Bytes | Description | Notes |
| :--- | :---: | :--- | :--- |
| **31D8** | 1 | Low Cam Rev Limiter | Low cam engine RPM fuel cut (uses OBD0 8-bit RPM formula) |
| **31DE** | 1 | High Cam Rev Limiter | Warm/VTEC engine RPM fuel cut (uses OBD0 8-bit RPM formula) |
| **31E0** | 1 | High Cam Rev Recovery | RPM where VTEC fuel cut recovers |
| **3418** | 1 | VTEC Disengage Speed | Lower VTEC cut-off speed threshold (uses OBD0 VTEC formula) |
| **3419** | 1 | VTEC Engage Speed | VTEC engagement speed threshold |
| **3BE6** | 255 | Low Cam Ignition Map | 15x17 low cam ignition advance map (uses OBD0 Ignition formula) |
| **3CE5** | 255 | High Cam Ignition Map | 15x17 VTEC ignition advance map (first row is typically empty filler) |
| **3DE4** | 255 | Low Cam Fuel Table | 15x17 base fueling lookup map (uses OBD0 Fuel formula) |
| **3EE3** | 15 | Low Cam Multipliers | Column multiplier coefficients for fuel map 1 |
| **3EF2** | 255 | High Cam Fuel Table | 15x17 VTEC fueling lookup map (uses OBD0 Fuel formula) |
| **3FF1** | 15 | High Cam Multipliers | Column multiplier coefficients for VTEC fuel map |

> [!TIP]
> The OBD0 PR3 applies column multipliers to fuel maps to scale raw 8-bit cell values. Refer to the [Understanding Maps guide](/cars/fueling/understanding-maps) for information on load multiplier formulas.

---

## ECU Circuit Board Layouts

Refer to the following high-resolution board scans for diagnostic troubleshooting and repair of the PR3:

![JDM PR3 J01 OBD0 ECU top board view](pr3-j01-1.JPG)
*Top side component view of the JDM PR3 `J01` ECU board.*

![JDM PR3 J51 top board view showing microchip locations](pr3-j51top.jpg)
*Top side component view of JDM PR3 `J51` ECU board.*

![JDM PR3 J51 bottom solder trace view](pr3-j51bottom.jpg)
*Solder trace view on the bottom side of the PR3 `J51` board.*
