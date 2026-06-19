---
summary: 'Overview of hardware boards enabling Real-Time Programming (RTP) for Honda ECUs, including the EasyRTP v1.0 design.'
tags: [ecu, rtp, tuning, hardware]
complexity: beginner
---

# Real-Time Programmable ECU Boards

Real-time programmable boards allow for live calibration adjustments to the ECU without the need to physically remove or re-burn the ROM chip.

## Compatible Hardware

The following hardware designs are compatible with standard Honda ECU RTP implementations:

*   **EasyRTP v1.0:** A single-sided PCB adaptation of the original Doc design, utilizing the DS1230Y NVRAM chip.

> [!NOTE]
> Real-time programming requires specific ECU hardware modifications and compatible tuning software to interface with the memory emulator.

## Technical References

{{> rtp-setup-guide }}

::: widget error-codes :::
