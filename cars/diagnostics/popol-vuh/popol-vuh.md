---
summary: 'An overview of the Popol Vuh project, the foundational documentation effort that served as the catalyst for the Honda ECU tuning community knowledge base.'
tags: [ecu, history, reference, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Popol Vuh: Foundational ECU Documentation

The Popol Vuh project represents the origin of the centralized Honda ECU documentation effort. Originally compiled as a comprehensive spreadsheet, this data served as the primary technical foundation for mapping Honda engine management systems, sensor data, and diagnostic protocols.

## Project Significance

The Popol Vuh dataset provided the initial framework for decoding Honda OBD-0, OBD-1, and OBD-2 ECU architectures. By aggregating pinout data, memory addresses, and sensor scaling factors into a structured format, it enabled the community to transition from proprietary "black box" tuning to open-source diagnostic and modification capabilities.

> [!NOTE]
> This documentation serves as a historical reference for the evolution of Honda ECU tuning. For current diagnostic procedures, refer to the specific ECU hardware documentation.

## Core Data Components

The original dataset focused on the following technical areas:

*   **ECU Pinout Mapping:** Identification of signal paths for fuel injectors, ignition timing, and sensor inputs.
*   **Sensor Scaling:** Conversion factors for coolant temperature, intake air temperature, and manifold absolute pressure sensors.
*   **Diagnostic Protocols:** Early identification of error code triggers and communication handshakes.

## Technical Reference

For users looking to utilize the data derived from these foundational efforts, the following resources are available:

::: widget error-codes :::

{{> resistor-color-codes }}