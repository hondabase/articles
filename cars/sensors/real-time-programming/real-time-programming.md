---
summary: 'An overview of Real Time Programming (RTP) hardware solutions for Honda ECU tuning, enabling on-the-fly calibration changes.'
tags: [ecu, tuning, rtp, hardware, rom]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Real Time Programming (RTP) Hardware

Real Time Programming (RTP) allows for the modification of ECU calibration data while the engine is running, facilitating efficient tuning and live data adjustment.

## Hardware Solutions

The following hardware implementations are used to enable RTP functionality on supported Honda ECUs:

*   **Easy-RTP v1.0:** A single-sided adaptation of the original DS1230Y-based design.
*   **Easy-RTP Installation:** Procedures for installing the Easy-RTP v1.0 board into OBD1 ECUs.
*   **M5128 RAM Replacement:** A method involving the replacement of the 5128 XRAM 2K SRAM chip with a DS1220 NVSRAM.

> [!NOTE]
> The DS1220 NVSRAM implementation is an alternative RTP method currently under development.

## Related Documentation

*   [Easy-RTP v1.0 Specifications](/cars/rom/easy-rtp-v10)
*   [Easy-RTP Installation Guide](/cars/rom/easy-rtp-install)
*   [M5128 RAM Replacement Procedure](/cars/wiring/replace-m5128)
