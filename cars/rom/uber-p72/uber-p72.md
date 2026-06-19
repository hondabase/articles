---
summary: 'Technical reference for RAM and ROM address offsets specific to the UberData custom ROM codebase for OBD1 P72 ECUs.'
tags: [tuning, rom, software, p72, obd1]
applies_to:
  brand: Acura
  ecus: [P72]
  models: [integra]
  chassis: [dc2]
complexity: advanced
---

# Uber P72 ROM Map

The Uber P72 ROM is a modified Acura Integra GS-R P72 OBD1 ECU codebase designed for compatibility with the UberData tuning suite. This document outlines the RAM and ROM address offsets specific to UberData modifications.

> [!NOTE]
> For standard factory Honda/Acura P72 memory addresses, refer to the [P72 ROM Map](/cars/sensors/p72).

## RAM Address Mapping

The following table details the specific RAM locations utilized by the UberData custom code within the P72 ROM structure.

| Hex Offset | Length (Bytes) | Description | Notes |
| :---: | :---: | :--- | :--- |
| `645D` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
| `645F` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
| `6464` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
| `6466` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |

## Configuration Guidelines

When modifying these addresses, ensure the following:

* **Data Integrity:** Verify that the checksum is recalculated after any modifications to the ROM image.
* **Compatibility:** Ensure the UberData version matches the specific ROM base version to prevent memory conflicts.
* **Hardware:** Confirm the ECU is socketed correctly with a compatible EEPROM (e.g., 27SF512) before flashing.

> [!WARNING]
> Incorrect modification of RAM addresses can lead to ECU instability, engine misfire, or failure to start. Always maintain a backup of the original factory ROM image.
