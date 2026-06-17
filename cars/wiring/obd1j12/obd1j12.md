---
summary: 'Technical explanation of J12 jumper functionality on OBD1 Honda ECUs for datalogging and serial communication.'
tags: [ecu, wiring, serial-communication, datalogging]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: [dc2, eg, eg-eh]
complexity: intermediate
---

# OBD1 ECU J12 Jumper Reference

The **J12 jumper** on OBD1 Honda ECU circuit boards controls the operational mode of the ECU's internal serial port.

---

## Jumper Functionality

*   **Stock Configuration (Jumper Installed):** The ECU serial port operates in **half-duplex mode**. In this configuration, the receive (RX) and transmit (TX) lines are shared, which is sufficient for basic diagnostic communications using a standard diagnostic connector.
*   **Full-Duplex Modification (Jumper Removed):** Removing the `J12` jumper disconnects the RX and TX lines, allowing for **full-duplex communication**.

---

## Datalogging Requirements
For reliable, high-speed **datalogging**, the `J12` jumper must be removed. Full-duplex communication allows the PC to send commands to the ECU and receive responses simultaneously, enabling higher sample rates and more robust data transmission without command collisions on the serial line.

*Note: Removing `J12` will break communication with the factory diagnostic connector located under the dashboard.*
