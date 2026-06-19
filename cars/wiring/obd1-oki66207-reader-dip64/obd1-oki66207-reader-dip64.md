---
summary: 'Technical guide for dumping the internal ROM contents of a DIP64 Oki 66207 microcontroller using a custom reader interface.'
tags: [ecu, rom-dumping, reverse-engineering, hardware, obd1]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: advanced
---

# OBD1 Oki 66207 Reader (DIP64)

This guide outlines the procedure for building a custom reader to dump the internal ROM contents of a DIP64 Oki 66207 microcontroller found in OBD1 ECUs.

---

## Hardware Modification

The reader requires an ECU with a 66207 MCU, a 27C512 EPROM, a 1k Ohm resistor, wiring, and an RS232-to-TTL converter.

1.  **ECU Preparation:** If not already chipped, install a `74HC373` latch, EPROM socket, and a 1k Ohm resistor (`R54`).
2.  **Wiring:**
    *   Connect a wire from MCU pin 16 (A15) to EPROM pin 1. (Do not insert pin 1 of the EPROM into the socket).
    *   Connect MCU pin 19 (P2.2) to MCU pin 27 (`_EA`).
    *   Remove the `J1` jumper and replace it with a 1k Ohm resistor.
3.  **Setup:** Install a 27C512 EPROM programmed with the ROMREADER software into the socket.
4.  **PC Interface:** Connect the ECU to a PC using an RS232-to-TTL converter.

---

## ROM Dumping Procedure

1.  **Terminal Config:** Configure serial software to **4800 baud, 8 data bits, No parity, 1 stop bit (4800, N, 8, 1)**.
2.  **Execution:** Power on the ECU. If the address display does not start at `0000`, click RESET.
3.  **Extraction:** After approximately 1 second, the address counter will begin running. Wait for the counter to reach `8001`.
4.  **Save:** Click SAVE to export the dumped ROM data.

*If the process fails, reset the ECU and re-initialize the connection. This technique relies on specific MCU hardware vulnerabilities; verify all connections carefully before application.*
