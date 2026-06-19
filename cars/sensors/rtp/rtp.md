---
summary: 'Real Time Programmability (RTP) allows for live adjustments to ECU tuning parameters while the engine is actively running.'
tags: [ecu, tuning, rtp, programming]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Real Time Programmability (RTP)

Real Time Programmability (RTP) is the capability to modify ECU calibration data and tuning parameters while the ECU is actively controlling the engine. This allows for immediate feedback and adjustment during the tuning process without the need to power cycle the ECU or perform a traditional flash procedure.

> [!NOTE]
> RTP is distinct from traditional "flash" tuning, which requires the engine to be stopped and the ECU to be placed into a programming mode to update the memory.

## Supported Systems
While many modern standalone ECUs support RTP, implementation on factory-based hardware remains a specialized field. Systems currently supporting this functionality include:

*   **Zdyne SECU Gold:** A specialized aftermarket ECU solution designed for Honda applications.
*   **AEM EMS Standalone:** A fully programmable engine management system that allows for live mapping changes.

## Technical Objectives
Achieving RTP on stock Honda ECU hardware is a primary objective for advanced engine management development. This requires replacing the stock ROM with a re-writable memory medium (such as battery-backed RAM or Flash memory) and implementing a communication protocol that allows the host computer to write to memory addresses while the CPU is executing code from the same memory space.

> [!IMPORTANT]
> Implementing RTP on stock hardware requires hardware modifications to the ECU board, typically involving the installation of a daughterboard or memory emulator to intercept and manage memory access.
