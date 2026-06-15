---
summary: 'Technical reference and memory map offset guide for the John Cui High-Resolution (Hi-Res) P72 custom ROM modification.'
tags: [tuning, rom, software]
applies_to:
  brand: Acura
  ecus: [P72]
  obd: [1]
  models: [civic, integra]
  chassis: [dc2, eg]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Hi Res P72'
    url: /pgmfi/wiki/library/hi-res-p72
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# High-Resolution (Hi-Res) P72 ROM Specifications

The factory OBD1 Acura Integra GS-R P72 ECU utilizes fuel and ignition tables with different row and column grid dimensions compared to the Civic P28 ECU. This size difference makes it difficult to directly copy and paste calibrated maps between P28 and P72 files.

The **Hi-Res P72 ROM** is a custom-modified P72 ROM binary (pioneered by John Cui) that adjusts the ECU\'s lookup table code. By redefining the size of the P72's internal lookup tables to match the P28 standard, it allows tuners to transfer map tables directly between P28 and P72 calibrations without interpolation errors.

---

## Memory Offset Map (RAM & ROM Locations)

When writing custom plugins or scripts to modify a Hi-Res P72 ROM, developers must reference these specific memory addresses. These addresses differ from standard, factory P72 ROM maps:

| Hex Location | Length (Bytes) | Description | Notes |
| :---: | :---: | :--- | :--- |
| **`0x0A50`** | 2 | Location reference to low cam RPM value vector | John Cui's Hi-Res P72 |
| **`0x0A68`** | 2 | Location reference to high cam RPM value vector | John Cui's Hi-Res P72 |
| **`0x0A71`** | 1 | Length of high cam RPM value vector | John Cui's Hi-Res P72 |
| **`0x0A80`** | 2 | Location reference to high cam RPM value vector (alternate) | John Cui's Hi-Res P72 |
| **`0x0A89`** | 1 | Length of high cam RPM value vector (alternate) | John Cui's Hi-Res P72 |
| **`0x0AA3`** | 2 | Reference to MAP value vector | John Cui's Hi-Res P72 |
| **`0x0AB8`** | 2 | Reference to MAP value vector (alternate) | John Cui's Hi-Res P72 |
| **`0x0ACD`** | 2 | Reference to MAP value vector (alternate) | John Cui's Hi-Res P72 |
| **`0x1269`** | 2 | High Cam Fuel Map Config, Row Size | John Cui's Hi-Res P72 |
| **`0x1277`** | 2 | Jump location of high cam fuel lookup | John Cui's Hi-Res P72 |
| **`0x128B`** | 2 | Jump location of low cam fuel lookup | John Cui's Hi-Res P72 |
