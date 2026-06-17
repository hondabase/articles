---
summary: "A reference guide to real-time programmable hardware boards compatible with Honda ECU systems, including the Easy-RTP v1.0 design."
tags: [ecu, rtp, tuning, hardware, rom]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Real-Time Programmable ECU Boards

Real-time programmable (RTP) boards allow for on-the-fly calibration changes to the ECU without the need to physically remove or re-burn EPROM chips.

## Compatible Hardware

The following hardware designs are compatible with standard Honda ECU architectures for real-time tuning:

*   **Easy-RTP v1.0:** A single-sided PCB adaptation based on the original Doc/DS1230Y design.

> [!NOTE]
> Ensure that the chosen RTP board is compatible with your specific ECU hardware revision (e.g., OBD1 vs. OBD2) before installation.

## Technical Specifications

| Board Name | Base Design | PCB Type |
| :--- | :--- | :--- |
| Easy-RTP v1.0 | DS1230Y | Single-Sided |

{{> rtp-installation-guide }}