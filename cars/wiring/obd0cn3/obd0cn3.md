---
summary: 'Technical overview of the OBD0 ECU CN3 serial port, highlighting its functionality and pinout compatibility with OBD1 CN2.'
tags: [ecu, wiring, serial-communication, diagnostics]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# OBD0 CN3 Serial Port Reference

The **CN3** port is a 5-pin serial communication header found on most OBD0 Honda ECUs.

---

## Functionality
This port is functionally equivalent to the **CN2** serial port found on later OBD1 Honda ECUs. It is primarily used for:
*   **Data Logging:** Communicating real-time sensor data from the ECU to a PC-based tuning interface.
*   **ROM Modification:** Facilitating the reflashing or communication required for external EPROM tuning boards.

## Pinout Mapping
The pinout for the CN3 header largely mirrors the OBD1 CN2 standard. When wiring a data logging cable (e.g., using a USB-to-TTL adapter), ensure the transmit (TX) and receive (RX) lines are mapped correctly according to standard ECU communication pin-outs.

*Always verify your specific ECU board's silkscreen labels if available, as variations can occasionally occur between different ECU part numbers.*
