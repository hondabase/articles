---
summary: 'Pinout information and wiring reference for the OBD0 Acura Integra PR4 ECU (B18A1 engine).'
tags: [ecu, pinout, wiring, honda-integra]
applies_to:
  obd: [0]
  models: [integra]
  chassis: [da]
complexity: intermediate
---

# Acura Integra PR4 OBD0 ECU Pinouts

The OBD0 PR4 ECU was used in 1990–1991 Acura Integra models equipped with the B18A1 engine. 

While official factory service manuals often show full wiring harnesses rather than the individual ECU connector layout, this guide provides mapped signals derived from factory schematics and standard OBD0 electrical conventions.

---

## Mapped Connector Signals

### Emissions and EGR (California/Automatic Models)
California-spec Integra models with automatic transmissions utilize an EGR system.
*   **Pin A10:** EGR Control Solenoid (Red wire).
*   **Pin C8:** EGR Valve Lift Sensor (Yellow wire).

### Standard Models (Manual/49-State)
On standard configurations, pins are repurposed for the Pressure Regulator Cutoff (PRC) system:
*   **Pin A10:** Pressure Regulator Cutoff (PRC) Solenoid Valve (Green/Yellow wire).

### Idle and Steering Controls
*   **Pin C9:** Power Steering Pressure Switch (Red wire). The ECU utilizes this signal to increase idle speed during high power steering loads.

---

## Technical Notes

*   **Data Link Connector (DLC):** The DLC signal wire (Light Blue) does not map to a standard verified pin in available factory documentation.
*   **Transmission Signals:** Factory manuals for manual-transmission models do not document automatic transmission-specific gear controls or lockup solenoids.
*   **Unused Wires:** Certain factory harness wires (notably Red/Blue and Orange/Black) are present in the schematics but do not connect to defined sensors on standard models.

*Always verify your specific wire colors and pin positions against a factory service manual for your specific chassis and production region before making modifications.*
