---
summary: 'A technical overview of Electrically Erasable Programmable Read-Only Memory (EEPROM) and its function in ECU calibration, data storage, and tuning.'
tags: [tuning, rom, eeprom, ecu, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# EEPROM Technical Overview

Electrically Erasable Programmable Read-Only Memory (EEPROM) is a type of non-volatile memory used in electronic control units (ECUs) to store calibration data, fuel maps, and ignition timing tables. Unlike standard EPROM chips that require ultraviolet light for erasure, EEPROM can be erased and reprogrammed electronically using a compatible ROM burner or ECU programming interface.

## Key Characteristics

*   **Non-Volatile:** Retains stored data even when power is removed from the ECU.
*   **Electrical Erasure:** Allows for rapid iteration during the tuning process without the need for physical UV exposure.
*   **In-Circuit Programming:** Depending on the ECU architecture, some EEPROM variants support being updated while installed on the PCB.

> [!NOTE]
> While EEPROM is often used interchangeably with Flash memory in modern contexts, they differ in their underlying cell architecture and endurance cycles. Always verify the specific chip part number when selecting a replacement or upgrade.

## Common Applications

EEPROM is utilized in Honda ECU tuning for:

*   **Fuel and Ignition Maps:** Storing the primary 2D and 3D tables that dictate engine performance.
*   **Sensor Scaling:** Holding calibration data for aftermarket sensors (e.g., MAP sensors, wideband O2 controllers).
*   **Diagnostic Data:** Storing fault codes and historical engine operating parameters.

## Handling and Programming

When working with EEPROM chips, ensure proper electrostatic discharge (ESD) precautions are taken to prevent data corruption or hardware failure.

> [!CAUTION]
> Ensure the ROM burner is set to the correct voltage and chip profile before initiating a write sequence. Incorrect voltage settings can permanently damage the EEPROM silicon.

{{> chip-programming-safety }}