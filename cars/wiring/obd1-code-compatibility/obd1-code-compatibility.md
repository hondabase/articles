---
summary: 'Guide to OBD1 ECU code compatibility, detailing VTEC requirements, sensor exclusions (O2/Knock), and regional (USDM/JDM/EDM) hardware differences.'
tags: [ecu, tuning, obd1, compatibility, wiring]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: [dc2, eg, eg-eh]
complexity: advanced
---

# OBD1 ECU Code Compatibility Guide

OBD1 Honda ECUs (92-95) share a standardized hardware platform, allowing for significant flexibility when running custom codebases. However, specific hardware-to-software requirements must be met for stable operation.

---

## Compatibility Rules

*   **VTEC Support:** VTEC-enabled ROMs require a VTEC-capable ECU. If using a non-VTEC ECU, you must perform a [Non-VTEC to VTEC conversion](/cars/wiring/non-vtec-to-vtec) or use a ROM with VTEC disabled.
*   **Non-VTEC ROMs:** These can run in VTEC-capable ECUs without modification.
*   **O2 Sensor Compatibility:** 1-wire O2 ECUs (e.g., P05, P08) require either a [hardware conversion](/cars/honda/civic/eg/wiring/one-wire-to4-wire-o2-sensor) or for the O2 Heater Circuit check to be disabled in the ROM.
*   **Knock Sensor:** DOHC VTEC programs (e.g., P30, P72) require a knock sensor circuit. If using an ECU lacking a knock board (e.g., P28, P08), you must disable the knock sensor check in the ROM.

---

## Regional ECU Differences

Different regional ECUs lack specific components that must be either physically added or disabled within the ROM:

| ECU Origin | Typical Hardware Exclusions | Required Mitigation |
| :--- | :--- | :--- |
| **USDM** | None (Most feature-complete) | N/A |
| **JDM** | Pressure Atmosphere (PA) Sensor, Electrical Load Detector (ELD), Injector Test Circuit. | Add components or disable in ROM. |
| **EDM** | Same as JDM, plus occasional lack of Knock Board/Sensor. | Add components or disable in ROM. |

---

## Technical Note
For detailed instructions on disabling specific sensor checks (Knock Sensor, O2 Heater, etc.) within your ROM, consult the specific [ROM Map](/cars/wiring/rom-maps) for your ECU codebase.
