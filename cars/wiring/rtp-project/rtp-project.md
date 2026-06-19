---
summary: 'An overview of the Real-Time Programming (RTP) project, which enables live ECU tuning and data acquisition for Honda OBD1 ECUs.'
tags: [ecu, tuning, rtp, hardware, datalogging]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
---

# Real-Time Programming (RTP) Project

The **Real-Time Programming (RTP)** project aims to enable live ECU tuning by replacing the static EPROM chip with an interface that allows for instantaneous map adjustments while the engine is running.

---

## Technical Overview
Traditional chip tuning requires removing the EPROM from the ECU, burning the data on an external programmer, and re-installing the chip. RTP replaces this process with an electronic module (typically utilizing NVSRAM) that interfaces directly with the ECU's memory bus.

### Key Features
*   **Live Tuning:** Allows tuners to modify fuel, ignition, and sensor tables in real-time without turning the engine off.
*   **Data Acquisition:** Integrates with datalogging software to allow for "on-the-fly" adjustments while monitoring sensor feedback.

## Hardware Requirements
Building an RTP module requires specific electronic components, including:
*   **Transceiver Chips:** High-speed chips (e.g., `MAX233` or `FT232BM`) to handle serial communication.
*   **Memory Modules:** NVSRAM chips (e.g., `STK14C88` or `U634H256`) to retain tune data.
*   **ECU Board Modifications:** Precise soldering and trace modifications are required to enable full-duplex communication and memory bus access.

*Warning: RTP hardware modification is an advanced task. Incorrect wiring or soldering can result in catastrophic ECU failure. Always perform thorough diagnostic testing of the module before connecting to a vehicle.*
