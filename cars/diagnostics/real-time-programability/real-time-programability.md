---
summary: 'Real-time programming (RTP) allows for live ECU calibration adjustments while the engine is running by replacing the standard EPROM with a programmable interface.'
tags: [ecu, tuning, rom, rtp, calibration]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Real-Time Programming (RTP) for Honda ECUs

Real-time programming (RTP) is a tuning methodology where the standard [EPROM](/cars/rom/eprom) of the [ECU](/cars/ecu/ecu) is replaced with a custom hardware interface. This system enables the tuner to modify fuel, ignition, and sensor parameters while the engine is actively running.

## Overview
Unlike traditional EPROM burning, which requires the ECU to be powered down and the chip to be physically removed or erased between iterations, an RTP system utilizes a dual-port RAM or similar memory emulation device. This allows an external laptop to communicate with the ECU's memory map in real-time.

> [!NOTE]
> RTP systems require specific tuning software capable of communicating with the hardware interface to synchronize data updates without causing ECU processor crashes or checksum errors.

## Key Components
*   **Emulator Hardware:** The physical board that replaces the factory EPROM chip.
*   **Communication Interface:** Typically a USB or serial connection between the laptop and the emulator.
*   **Tuning Software:** The application used to define the memory addresses and send calibration changes to the emulator.

## Operational Workflow
1.  **Initialization:** The RTP hardware is installed into the ECU's EPROM socket.
2.  **Connection:** The tuning laptop is connected to the RTP hardware via the designated communication port.
3.  **Live Calibration:** The tuner adjusts parameters (e.g., fuel maps, ignition timing) within the software.
4.  **Data Synchronization:** The software writes the changes to the emulator's memory, which the ECU reads instantly as the engine operates.

> [!IMPORTANT]
> Ensure the RTP hardware is properly grounded and shielded to prevent electrical noise from corrupting the data bus, which can lead to erratic engine behavior or ECU failure.