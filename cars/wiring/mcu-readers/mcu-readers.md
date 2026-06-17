---
summary: 'Technical overview of MCU reading methods, exploiting hardware design vulnerabilities in early Oki microcontrollers for ROM dumping.'
tags: [ecu, rom-dumping, reverse-engineering, hardware]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
---

# MCU Readers and ROM Dumping

This reference outlines the technical principles behind early Honda ECU MCU (Microcontroller Unit) readers, which utilize specific hardware design vulnerabilities in early Oki microcontrollers to dump internal program memory.

---

## Technical Principle

Oki MCUs can operate using either internal or external ROM. The selection is typically controlled by the state of the `_EA` (External Access) pin.

### The Design Vulnerability
Oki MCUs do not latch the state of the `_EA` pin upon power-up. This allows the internal ROM to be "unmasked" after the MCU has begun executing code.

### ROM Dumping Procedure
1.  **Hardware Prep:** Manually wire an I/O pin to the `_EA` pin of the MCU (using pull-up/pull-down resistors as necessary).
2.  **External ROM:** Utilize a ROM chip larger than the MCU's internal capacity to facilitate the dump.
3.  **Execution:** Initialize the serial port to establish communication.
4.  **Memory Unmasking:** Execute code that causes the MCU to jump to a memory address outside the masked ROM area, then flip the state of the `_EA` pin.
5.  **Data Extraction:** Implement a delay loop that allows the internal ROM to be re-masked into memory, then copy the ROM contents out through the serial port.

---

## Reader Designs
Several designs have been documented for different MCU packages and generations:

*   **OBD0 Oki83C154:** Standardized reader design.
*   **OBD1 Oki66207 (DIP64):** Designed for standard DIP package chips.
*   **OBD1 Oki66207 (PLCC68):** Designed for JDM SMT packages.
*   **OBD2 Oki66507:** Specialized reader for OBD2-era MCUs.

*Adjustment to these designs requires modifying the clock speed, board layout, and software routines to match the target chip's specifications.*
