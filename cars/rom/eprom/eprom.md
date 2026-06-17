---
summary: 'A technical reference for EPROM compatibility in OBD0 and OBD1 Honda ECUs, including common chip types and pin-compatibility requirements.'
tags: [ecu, tuning, rom, eprom, hardware]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eh]
complexity: beginner
---

# Honda ECU EPROM Compatibility Reference

EPROM (Erasable Programmable Read-Only Memory) is a type of non-volatile memory used to store ECU calibration data. These chips are programmed using a dedicated ROM burner.

## Compatible EPROM Types

The following chips are commonly used for Honda ECU tuning due to their pin-compatibility with standard OBD0 and OBD1 ECU sockets:

*   **27C256:** A standard UV-erasable EPROM.
*   **29C256:** An electrically erasable (EEPROM) alternative, often preferred for its ease of reprogramming.

> [!IMPORTANT]
> While the **28C256** is frequently encountered, it is **not** pin-compatible with standard OBD0/OBD1 Honda ECU sockets and should not be used as a direct replacement.

## Technical Specifications

| Chip Model | Type | Erasure Method | Compatibility |
| :--- | :--- | :--- | :--- |
| 27C256 | EPROM | UV Light | OBD0/OBD1 |
| 29C256 | EEPROM | Electrical | OBD0/OBD1 |
| 28C256 | EEPROM | Electrical | Not Compatible |

> [!TIP]
> When selecting a chip for ECU tuning, ensure the access time (measured in nanoseconds, e.g., 120ns or 150ns) meets or exceeds the requirements of the ECU's processor to prevent data read errors.

## Related Components
*   **[ROM Burner](/cars/ecu/rom-burner):** Hardware required to write data to the EPROM.
*   **[ECU](/cars/ecu/ecu):** The target engine control unit requiring the programmed chip.