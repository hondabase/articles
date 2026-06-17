---
summary: 'An overview of Read Only Memory (ROM) architecture and its role in Honda engine control unit (ECU) firmware storage.'
tags: [tuning, rom, ecu, firmware]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Read Only Memory (ROM) Architecture

Read Only Memory (ROM) serves as the non-volatile storage medium for the ECU's operating instructions, fuel maps, ignition timing tables, and sensor calibration data. In the context of Honda engine management, the ROM contains the "firmware" that dictates how the engine operates under various load and environmental conditions.

## Technical Overview

The ROM chip is a permanent storage device. Unlike Random Access Memory (RAM), which is volatile and cleared when power is removed, the data stored in ROM remains intact even when the ECU is powered down.

### Key Characteristics
*   **Non-Volatile:** Data retention does not require a constant power source.
*   **Read-Only:** Under normal operating conditions, the ECU can only read data from the chip; it cannot write or modify the data stored within it.
*   **Firmware Integrity:** The data stored in the ROM is "carved in stone," meaning it is static and provides the baseline logic for the engine's performance.

## ROM Types in Honda ECUs

Depending on the generation and specific ECU hardware, different types of memory chips are utilized:

*   **Mask ROM:** Factory-programmed during the manufacturing process. These chips cannot be altered or reprogrammed.
*   **EPROM (Erasable Programmable Read-Only Memory):** Can be erased using ultraviolet (UV) light and reprogrammed using an external programmer. These are commonly found in socketed ECUs used for tuning.
*   **EEPROM (Electrically Erasable Programmable Read-Only Memory):** Can be erased and reprogrammed electrically. These are more modern and allow for easier updates compared to EPROM.
*   **Flash Memory:** Found in later OBD2 and newer ECUs, allowing for in-circuit reprogramming without removing the chip from the board.

> [!IMPORTANT]
> When modifying or "chipping" an ECU, the original Mask ROM is typically replaced with a socketed EPROM or EEPROM to allow for custom fuel and ignition mapping.

## Data Structure

The data within the ROM is organized into specific memory addresses. The ECU's microprocessor references these addresses to retrieve instructions or look up values in tables (e.g., a 2D fuel table or a 3D ignition map).

| Memory Type | Erasability | Typical Use Case |
| :--- | :--- | :--- |
| **Mask ROM** | None | Factory stock ECUs |
| **EPROM** | UV Light | OBD1 Chipped ECUs |
| **EEPROM** | Electrical | OBD1/OBD2 Tuning |
| **Flash** | Electrical | OBD2+ / Modern ECUs |

> [!TIP]
> Always ensure the correct chip type and capacity (e.g., 27C256 or 27C512) are used when performing ECU modifications to ensure compatibility with the ECU's memory mapping.