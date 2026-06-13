---
summary: 'An index of Honda and Acura ECU connector pinouts, wiring diagrams, and harness conversion guides across OBD0, OBD1, and OBD2 generations.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - pinout
  - wiring
---

# Index of Honda ECU Connections & Pinouts

Wiring harnesses, plugs, and pin layouts vary significantly between generations of Honda engine control units. Knowing these pin connections is required for engine swaps, custom sensor additions (such as wideband controllers or EGT logging), and manual transmission conversions.

Below is an index of wiring diagrams, pinouts, and custom harness modifications categorized by OBD generation.

---

## 1. OBD0 Generation (1988–1991)

OBD0 ECUs use three yellow harness plugs (Connector A, B, and C) to interface with the vehicle.
*   **PR4 Layouts:** For B18A1-powered vehicles, see the [Acura Integra PR4 ECU Pinout and Schematics](/cars/electronics/acura-integra-pr4ecu-pinout-and-schematics) guide.
*   **Harness Swaps:** To upgrade an OBD0 chassis to run a newer OBD1 ECU, refer to [Kurt's OBD0-to-OBD1 Conversion Guide](/cars/electronics/kurts-obd0-obd1).

---

## 2. OBD1 Generation (1992–1995)

OBD1 ECUs standardize on three grey plugs (A, B, and D pins) and represent the most popular era for custom tuning.

### Custom Switch Modifications
*   **A/C Request Switch Bypass:** How to wire and trigger the A/C input line (Pin B5) on vehicles not equipped with factory air conditioning. This is often used by tuners to activate secondary maps (such as a valet mode or wet-weather map).
*   **Full-Throttle Shift Switch:** Utilizing the factory clutch switch or cruise control cancel switch to feed a ground signal to the ECU (typically Pin B8 or D10) to trigger flat-foot shifting algorithms in Crome or Hondata.

---

## 3. OBD2 Generation (1996–2001)

OBD2 layouts are split into two distinct pin configurations (OBD2A for 1996–1998 vehicles and OBD2B for 1999–2001 vehicles).

*   **OBD2-to-OBD1 Conversions:** Because OBD2 ECUs are locked and cannot be chipped, tuners use a plug-and-play conversion harness to adapt the vehicle's OBD2 plugs to an OBD1 ECU.
*   **Accord Conversions:** For Accord-specific swaps, see the [Accord OBD2-to-OBD1 Auto-to-Manual Guide](/cars/electronics/accord-auto-obd2-obd1).

---

## 4. Archived Files & Downloads

For reference when wiring a mid-generation Civic or Integra:

*   [Download the USDM Civic 1996–1998 OBD2 Pinout PDF](OBD2Pinout.pdf) *(615 KB, detailed OBD2A connector pinout reference)*
