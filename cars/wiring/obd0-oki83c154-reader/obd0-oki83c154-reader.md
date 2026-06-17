---
summary: 'Technical guide for dumping the internal ROM contents of an Oki 83C154 microcontroller, used in certain OBD0 ECUs.'
tags: [ecu, rom-dumping, reverse-engineering, hardware]
applies_to:
  obd: [0]
  models: [civic, crx]
  chassis: [ef]
complexity: advanced
---

# OBD0 Oki 83C154 ROM Dumping Guide

This guide details the procedure for dumping the internal program memory of the Oki 83C154 microcontroller, commonly found in OBD0 Honda ECUs.

---

## Hardware Requirements

*   **External Connection:** The target MCU must be connected to an external EPROM.
*   **Serial Interface:** A `MAX233` (or compatible) serial level shifter is required to facilitate communication between the ECU and a PC.
*   **Hardware Modification:**
    1.  Open the `_EA` (External Access) jumper on the ECU board.
    2.  Connect the `_EA` line of the MCU to pin `P1.7` of the MCU.

---

## ROM Dumping Procedure

1.  **Preparation:** Configure your serial terminal software to **4800 baud, No parity, 8 data bits, 1 stop bit (4800, N, 8, 1)**.
2.  **Code Execution:** Run the specialized dumping code which performs the following:
    *   Jumps to memory address `4100h`.
    *   Flips the state of the `_EA` pin (using `P1.7` to mask/unmask the internal ROM).
    *   Enters a delay loop to allow the internal ROM to be mapped into the memory space at `0000h`–`4000h`.
3.  **Data Extraction:** Copy the contents of the memory range via the serial port.
4.  **Verification:** Analyze the downloaded dump to verify the integrity of the data, specifically looking for fuel and ignition tables.

*Note: This process relies on hardware design vulnerabilities to bypass internal mask-ROM read protection. Ensure your wiring is correct before applying power to avoid damaging the MCU.*
