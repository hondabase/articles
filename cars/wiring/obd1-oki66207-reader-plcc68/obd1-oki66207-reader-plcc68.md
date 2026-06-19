---
summary: 'Technical guide for dumping the internal ROM contents of a PLCC68 Oki 66207 microcontroller using a custom reader interface.'
tags: [ecu, rom-dumping, reverse-engineering, hardware, obd1]
applies_to:
  models: [civic, del-sol]
  chassis: [eg, eg-eh]
complexity: advanced
---

# OBD1 Oki 66207 Reader (PLCC68)

This guide details the procedure for dumping the internal ROM contents of a PLCC68-packaged Oki 66207 microcontroller, often found in certain JDM OBD1 ECUs. The process is similar to the DIP64 reader method, but with specific mapping adjustments for the PLCC68 configuration.

---

## Hardware Modification

1.  **ECU Preparation:** Ensure the ECU is chipped with a `74HC373` latch, EPROM socket, and a 1k Ohm resistor (`R54`).
2.  **Wiring:**
    *   Connect a wire from MCU pin 17 (A15) to EPROM pin 1. (Do not insert pin 1 of the EPROM into the socket).
    *   Connect MCU pin 21 (P2.2) to MCU pin 29 (`_EA`).
    *   Cut the PCB trace on pin 29 and replace it with a 1k Ohm resistor.
3.  **Setup:** Install a 27C512 EPROM programmed with the ROMREADER software into the socket.
4.  **PC Interface:** Connect the ECU to a PC using an RS232-to-TTL converter.

---

## ROM Dumping Procedure

1.  **Terminal Config:** Configure serial software to **4800 baud, 8 data bits, No parity, 1 stop bit (4800, N, 8, 1)**.
2.  **Execution:** Power on the ECU. If the address display does not start at `0000`, click RESET.
3.  **Extraction:** After approximately 1 second, the address counter will begin running. Wait for the counter to reach `8001`.
4.  **Save:** Click SAVE to export the dumped ROM data.

*After the dump is successful, remember to solder the cut PCB track to re-enable normal external ROM functionality.*
