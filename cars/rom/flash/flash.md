---
summary: 'An overview of FLASH memory technology, explaining its sector-based erase and write operations in the context of automotive ECU tuning.'
tags: [tuning, rom, memory, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# FLASH Memory Architecture

FLASH memory functions similarly to EEPROM; however, it is distinguished by its requirement to be erased and written in specific blocks known as sectors.

## Operational Characteristics

Unlike byte-addressable EEPROM, FLASH memory utilizes a sector-based architecture. This means that individual bytes cannot be modified in isolation; instead, the entire sector must be erased before new data can be written to that memory range.

> [!IMPORTANT]
> When performing ECU reflashing, ensure the programming tool supports sector-level management to prevent data corruption or incomplete write cycles.

## Comparison Table

| Feature | EEPROM | FLASH |
| :--- | :--- | :--- |
| **Erase Granularity** | Byte-level | Sector-level |
| **Write Speed** | Slower | Faster |
| **Density** | Lower | Higher |
| **Typical Use** | Calibration data | Firmware/Map storage |

> [!TIP]
> Because FLASH requires sector-level erasing, always verify the integrity of the entire sector after a write operation to ensure no data was lost during the block-erase process.
