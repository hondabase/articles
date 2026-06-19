---
summary: 'Wiring conversion guide and pinout translation tables for running an automatic OBD2a Honda Accord using an automatic OBD1 Integra ECU and separate TCU.'
tags: [conversion, wiring, automatic-transmission, ecu-tuning, obd2]
applies_to:
  models: [accord]
  chassis: [cb-cd]
complexity: advanced
---

# Automatic Accord OBD2-to-OBD1 Conversion Guide

Unlike Honda Civics of the same era, which integrate transmission lockup controls within the ECU, automatic Honda Accords utilize a separate **Transmission Control Unit (TCU)**. 

When converting a USDM 5th-generation (1996–1997) automatic Accord from OBD2a to OBD1 for tuning (e.g., adding forced induction), standard manual-transmission OBD2-to-OBD1 jumper harnesses are insufficient because they do not route the essential TCU communication signals. 

This guide outlines the components, pin mapping, and harness construction required for this conversion.

---

## 1. Required Components

To run an automatic OBD2a Accord on an OBD1 ECU and TCU, you will need:

*   **Automatic OBD1 P75 ECU:** An automatic ECU from a 1994–1995 Integra (P75-A5x for 49-state, P75-L5x for California).
*   **OBD1 Accord TCU:** An automatic TCU from a 1994–1995 non-VTEC Accord (F22B2 engine).
*   **Chipped EPROM:** A ROM bin file compatible with the automatic Integra ROM and your specific engine configuration.
*   **Wiring Schematics:** Factory service manuals for the 1994–1995 Accord (TCU), 1994–1995 Integra (ECU), and 1996 Accord (Engine harness).

> **Warning:** This conversion requires precise electrical connections. Verify every pin against your specific factory service manuals before applying power. Incorrect wiring can damage the ECU, TCU, harness, or vehicle electronics.

---

## 2. Harness Construction Requirements

To fabricate a custom conversion harness, you will need:

*   **Wire:** 20 AWG (general signals) and 18 AWG (power/ground lines).
*   **Connectors:** 
    *   **OBD1 ECU Plugs:** Two 26-pin, two 22-pin, and one 16-pin Tyco/AMP connectors.
    *   **OBD2a Header:** One 104-pin male pin header (sourced from a scrap OBD2a ECU or new).
*   **Terminals:** Appropriate small and large contact pins suitable for the selected connectors.
*   **Tools:** Standard open-barrel terminal crimping tool.

---

## 3. Pinout Translation Table (Reference)

The following table maps the 1996–1997 OBD2a Accord engine harness signals to the required OBD1 P75 ECU and OBD1 F22B2 TCU pins:

| OBD2a Accord Pin | TCU Pin | OBD1 P75 ECU Pin | Signal Name |
| :--- | :--- | :--- | :--- |
| **A01** | - | **A02** | Injector 4 Control |
| **A02** | - | **A05** | Injector 3 Control |
| **A03** | - | **A03** | Injector 2 Control |
| **A04** | - | **A01** | Injector 1 Control |
| **A06** | - | **A06** | Primary O2 Sensor |

*(Note: Ensure all power and ground lines are cross-referenced with your specific year/model service manuals.)*
