---
summary: 'An overview of Honda OBD0, OBD1, and OBD2 diagnostic systems, highlighting key differences, connector layouts, and code retrieval methods.'
tags: [obd, reference, wiring, diagnostics, honda-tuning]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [dc2, ef, eg, eg-eh, ek]
complexity: beginner
---

# Honda OBD Generations Guide (OBD0 to OBD2)

Understanding the evolution of Honda's On-Board Diagnostics (OBD) systems is essential for mechanics, engine swappers, and performance tuners. These generations reflect Honda's development of PGM-FI (Programmed Fuel Injection) to meet changing emission standards and diagnostic requirements.

---

## 1. OBD0 Systems (1988–1991)

OBD0 represents the first generation of electronic fuel injection for Honda, found in vehicles like the 4th-generation Civic (EF), CRX, and 2nd-generation Integra (DA).

### Key Characteristics
*   **Basic Monitoring:** System checks are limited to basic high/low voltage thresholds (detecting circuit opens or shorts).
*   **Diagnostics:** Does not use the dashboard Check Engine Light (CEL) for code flashing.
*   **Sensor Setup:** Often utilizes simple 1-wire unheated oxygen sensors or early heated configurations.

### Retrieving Trouble Codes
1.  Locate the ECU (typically under the passenger footwell carpet).
2.  Turn the ignition key to the ON position.
3.  Observe the red LED through the viewing window in the ECU metal casing.
4.  Count the LED flashes. For example, 9 flashes indicate a Cylinder Position Sensor fault.

---

## 2. OBD1 Systems (1992–1995)

OBD1 is highly regarded in the tuning community, particularly for the 5th-generation Civic (EG) and 3rd-generation Integra (DC), due to its standardized motherboard architecture which is easily modified.

### Key Characteristics
*   **Rationality Checks:** The ECU compares sensor inputs to ensure values remain logical relative to current engine conditions.
*   **Heated O2 Sensors:** Standardized use of 4-wire heated oxygen sensors to improve emissions performance during warmup.
*   **Diagnostics:** Uses the dashboard CEL to flash diagnostic codes via the Service Connector Switch (SCS).

### Retrieving Trouble Codes
1.  Locate the 2-pin Service Connector (SCS) (typically behind the passenger-side kick panel).
2.  Bridge the two pins with a jumper wire or paperclip.
3.  Turn the ignition key to the ON position.
4.  Count the flashes on the dashboard CEL:
    *   **Long flashes:** Represent the tens digit (e.g., three long = 30).
    *   **Short flashes:** Represent the units digit (e.g., four short = 4).
    *   Example: Code 23 (Knock Sensor) = two long, three short.

---

## 3. OBD2 Systems (1996–2001)

Introduced to comply with standardized EPA mandates, OBD2 vehicles utilize a 16-pin Data Link Connector (DLC) and report standardized DTCs (e.g., `P0420`).

### Key Characteristics
*   **Downstream Monitoring:** Adds a secondary oxygen sensor after the catalytic converter to monitor its efficiency.
*   **Protocol:** Standardized diagnostic protocol and DTC reporting.
