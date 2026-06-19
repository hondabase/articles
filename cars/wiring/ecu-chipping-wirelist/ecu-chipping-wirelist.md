---
summary: 'Technical wirelist for OBD1 Honda ECU chipping, detailing connections for 74HC373 latch and ROM sockets.'
tags: [ecu, chipping, hardware, wiring]
applies_to:
  models: [civic, del-sol]
  chassis: [eg, eg-eh]
complexity: advanced
---

# OBD1 ECU Chipping Wirelist

This document serves as a technical reference for diagnosing continuity issues after installing an external ROM socket and `74HC373` latch on an OBD1 Honda ECU. It outlines verified connections between the latch, ROM socket, 66K MCU, and support components.

> **Caution:** Always disconnect the ECU from the vehicle before performing continuity testing.

## Testing Procedure
1.  **Inspect:** Visually verify the `74HC373` latch and ROM socket for solder bridges.
2.  **Adjacent Pin Test:** Use a continuity tester to ensure no adjacent pins on the packages have continuity.
3.  **Point-to-Point Test:** Test for continuity between each package pin and its expected connection point using the wirelist below.

## Wiring Reference

| ECU Variant | Component | Pin | Signal | Path Reference |
| :--- | :--- | :--- | :--- | :--- |
| **JDM P30-901** | 373 Latch | 1 | /OE | 373 Pin 10 -> FT -> ROM Pin 14 |
| **JDM P30-901** | 373 Latch | 2 | 1Q | RM3 Pin 5 -> ROM Pin 10 (A0) |
| ... | ... | ... | ... | ... |

*(The wirelist is extensive; refer to the raw data files for full pin-to-pin mapping)*

---

## Technical Notes
*   **DIP Pins:** Numbering begins at pin 1 beside the notch or dot, running down the left side, then up the right side.
*   **RM3:** Single-inline-package resistor pack; pin 1 is indicated on the silkscreen.
*   **JDM P30-901:** Square surface-mount MCU pin 1 is in the center of one side.
*   **Active Low Signals:** Signal names beginning with `/` are active low.
