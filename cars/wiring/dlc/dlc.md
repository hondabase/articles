---
summary: 'Technical reference and location guide for the Honda 3-pin (OBD0/OBD1) and standardized 16-pin (OBD2) Data Link Connectors (DLC).'
tags: [diagnostics, wiring, communication-interface]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, del-sol, integra, prelude]
complexity: intermediate
---

# Honda Data Link Connector (DLC) Reference

The **Data Link Connector (DLC)** is the diagnostic interface port used to communicate with Honda Engine Control Units (ECUs). Depending on the vehicle's model year and On-Board Diagnostics (OBD) generation, Honda utilizes either a proprietary legacy 3-pin connector or the standardized SAE 16-pin J1962 connector.

---

## 3-Pin Data Link Connector (OBD0/OBD1)

On OBD0 and OBD1 vehicles (roughly 1988–1995), Honda utilized a proprietary **3-pin DLC** port to transmit serial K-Line diagnostic data.

### Configuration
*   **3-Wire Models:** Include a constant +12V power supply, ground, and a serial data line. This allows diagnostic scanners to power directly from the port.
*   **2-Wire Models:** Contain only the ground and serial data lines. Diagnostic tools used on these models must be powered by an external source.
*   **Service Check Connector (SCS):** The 3-pin DLC is located adjacent to a separate **2-pin blue connector**. Shorting the SCS connector (with a jumper or paperclip) is the standard method for reading flashing diagnostic codes on the dashboard CEL.

### Common Locations
*   **1992–1995 Civic / 1993–1995 del Sol:** Right lower edge of the passenger dash.
*   **1994–1995 Accord (L4):** Right lower edge of the passenger dash.
*   **1992–1995 Prelude:** Behind the front of the center console.
*   **1995 Odyssey:** Behind the passenger glove box.

---

## 16-Pin Data Link Connector (OBD2)

Honda adopted the standardized **16-pin OBD2 DLC** (SAE J1962) beginning with the V6 Accord in 1995, and it became standard on all USDM vehicles by 1996.

### Technical Details
*   **Communication Protocol:** Honda utilizes the **ISO 9141-2** protocol for OBD2 communications, primarily using Pins 7 (K-Line) and 15 (L-Line).
*   **Pin Configuration:** While 16 pins are present, Honda typically populates only 7 for standard emissions diagnostics. Other pins are reserved for proprietary systems (ABS, SRS, etc.).

### Common Locations
*   **Under Driver Dashboard (Facing Down):** 1998–2002 Accord, 1996–2000 Civic, 1996–1997 Passport.
*   **Behind Center Console Ashtray/Trim:** 1995–1997 Accord (V6/L4), 1996–1997 Odyssey, 1996–1997 del Sol, 1997–2001 CR-V, 1997–2001 Prelude.
