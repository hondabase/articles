---
summary: 'Technical reference and memory map offset guide for the John Cui High-Resolution (Hi-Res) P72 custom ROM modification, enabling P28-compatible table scaling.'
tags: [tuning, rom, ecu, p72]
applies_to:
  brand: Acura
  ecus: [P72]
  obd: [1]
  models: [integra]
  chassis: [dc2]
complexity: advanced
---

# High-Resolution (Hi-Res) P72 ROM Specifications

The factory OBD1 Acura Integra GS-R P72 ECU utilizes fuel and ignition tables with different row and column grid dimensions compared to the Civic P28 ECU. This discrepancy prevents the direct transfer of calibrated maps between P28 and P72 files.

The **Hi-Res P72 ROM** is a custom-modified P72 ROM binary that adjusts the ECU's lookup table code. By redefining the size of the P72's internal lookup tables to match the P28 standard, it allows tuners to transfer map tables directly between P28 and P72 calibrations without interpolation errors.

> [!IMPORTANT]
> This modification is intended for advanced tuning applications. Ensure the checksum is recalculated after applying these ROM modifications to prevent ECU boot errors.

## Memory Offset Map

When developing custom plugins or scripts to modify a Hi-Res P72 ROM, use the following memory addresses. These offsets are specific to the Hi-Res implementation and differ from factory P72 specifications.

| Hex Location | Length (Bytes) | Description | Notes |
| :--- | :---: | :--- | :--- |
| **`0x0A50`** | 2 | Low cam RPM value vector reference | Hi-Res P72 |
| **`0x0A68`** | 2 | High cam RPM value vector reference | Hi-Res P72 |
| **`0x0A71`** | 1 | High cam RPM value vector length | Hi-Res P72 |
| **`0x0A80`** | 2 | High cam RPM value vector reference (alt) | Hi-Res P72 |
| **`0x0A89`** | 1 | High cam RPM value vector length (alt) | Hi-Res P72 |
| **`0x0AA3`** | 2 | MAP value vector reference | Hi-Res P72 |
| **`0x0AB8`** | 2 | MAP value vector reference (alt) | Hi-Res P72 |
| **`0x0ACD`** | 2 | MAP value vector reference (alt) | Hi-Res P72 |
| **`0x1269`** | 2 | High cam fuel map configuration, row size | Hi-Res P72 |
| **`0x1277`** | 2 | High cam fuel lookup jump location | Hi-Res P72 |
| **`0x128B`** | 2 | Low cam fuel lookup jump location | Hi-Res P72 |