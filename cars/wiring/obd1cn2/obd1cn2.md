---
summary: 'Technical reference for the OBD1 ECU CN2 serial port, detailing its pinout and role in datalogging.'
tags: [ecu, wiring, serial-communication, diagnostics]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: intermediate
---

# OBD1 CN2 Serial Port Reference

The **CN2** header is the dedicated 5-pin serial communication port found on OBD1 Honda ECUs. It serves as the primary interface for ECU-to-PC communication, essential for real-time datalogging and ROM programming.

---

## Pinout Mapping

| Pin | Function | Description |
| :---: | :--- | :--- |
| **1** | GND | Ground |
| **2** | RX | Receive (from PC) |
| **3** | +5V | Logic Power |
| **4** | TX | Transmit (to PC) |
| **5** | N.C. | Not Connected |

---

## Operational Notes
*   **Half-Duplex:** In stock form, the CN2 port operates in half-duplex mode (RX and TX are shared/connected).
*   **Full-Duplex Modification:** Removing the **J12** jumper on the ECU board separates the receive and transmit lines, enabling full-duplex communication. This is recommended for more reliable high-speed datalogging.
*   **Hardware Interface:** The ECU communicates at **TTL (5V logic)** voltage levels. An appropriate RS232-to-TTL signal translator is required to interface with standard PC serial or USB ports.

*Always verify your board layout and silkscreen labels if available, as variations can occasionally occur between different ECU part numbers.*
