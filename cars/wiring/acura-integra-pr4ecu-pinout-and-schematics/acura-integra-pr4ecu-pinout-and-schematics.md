---
summary: 'Wiring layout, pinout details, and schematic analysis for the OBD0 and OBD1 Acura Integra PR4 ECU.'
tags: [ecu, pinout, schematic]
applies_to:
  obd: [0, 1]
  models: [integra]
  chassis: [da, dc2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Acura Integra PR4ECU Pinout And Schematics'
    url: /pgmfi/wiki/library/acura-integra-pr4ecu-pinout-and-schematics
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Acura Integra PR4 OBD0 ECU Pinouts and Wiring

The OBD0 PR4 ECU was used in the 1990 and 1991 Acura Integra equipped with the B18A1 engine. Finding a complete, official pinout schematic for this specific ECU can be difficult, as many factory manuals only show full wiring harnesses rather than the individual ECU connector layout. 

By analyzing the factory 1990–1991 Integra engine control system schematics, wire colors, and functions can be cross-referenced with general OBD0 ECU standards to map key pins.

## Mapped Connector Signals

The following pins have been verified using wire color codes and standard OBD0 electrical paths:

### Exhaust Gas Recirculation (EGR) (California Models Only)
California-spec Integra models equipped with automatic transmissions feature an EGR system. These use the following pin assignments:
*   **Pin A10:** EGR Control Solenoid (Red wire)
*   **Pin `C8`:** EGR Valve Lift Sensor (Yellow wire)

### Pressure Regulator Cutoff
On standard manual transmission and non-California models, the EGR pins are repurposed or omitted:
*   **Pin A10:** Pressure Regulator Cutoff (PRC) Solenoid Valve (Green/Yellow wire)

### Steering Switch Signal
*   **Pin `C9`:** Power Steering Pressure Switch (Red wire), used by the ECU to increase idle speed when steering load is high.

## Unresolved Wiring & Missing Pins

Some connections in the factory manuals do not map directly to standard OBD0 pins or are not fully documented:
*   **Data Link Connector (DLC):** The OBD0 Data Link Connector wire (Light Blue) is not mapped to a verified pin in standard documentation.
*   **Automatic Transmission Signals:** Pin layouts for automatic transmission gear controls and lockup solenoids are omitted from standard manual transmission wiring guides.
*   **Terminated Wires:** Two factory harness wires (**Red/Blue** and **Orange/Black**) appear in the schematics but do not connect to defined pins or sensors on standard models.
