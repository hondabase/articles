---
summary: 'A comprehensive memory mapping reference sheet of internal RAM, bit flags, and XRAM registers for OBD0 PM6 and PM7 Honda ECUs.'
tags: [rom, reference, obd0, tuning]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [ef]
complexity: advanced
---

# OBD0 PM6 & PM7 RAM Address Locations

This reference sheet outlines the internal memory-mapped address spaces of the **PM6** (USDM 1988–1991 Civic/CRX Si) and **PM7** (JDM DOHC ZC) OBD0 Honda ECUs. 

These ECUs utilize 8051-derivative microcontrollers, which partition memory into internal RAM, bit-addressable spaces, and external RAM (XRAM). This mapping is critical for reverse-engineering fuel/ignition maps, writing custom datalogging code, or modifying factory ROM routines.

## 8-Bit Internal RAM Locations (Bytes)

Below are the key 8-bit registers located in the primary internal RAM space:

| Address | Parameter / Short Name | Notes & Functions |
| :---: | :--- | :--- |
| **`0x2C.1`** | MAP High CEL | Bit flag; set to 1 if the MAP sensor reading exceeds safe parameters. |
| **`0x30`** | ECT Complement | Bitwise complement of `0x31h` (verifies ECT signal integrity). |
| **`0x31`** | ECT | Engine Coolant Temperature sensor reading (mirrors `XRAM 0x1004h`). |
| **`0x32`** | IAT | Intake Air Temperature sensor reading (mirrors `XRAM 0x1005h`). |
| **`0x33`** | IAT Complement | Bitwise complement of `0x32h` (verifies IAT signal integrity). |
| **`0x34`** | BARO | Barometric Pressure (PA sensor on board). |
| **`0x36`** | MAP | Manifold Absolute Pressure sensor reading. |
| **`0x37`** | MAP Complement | Bitwise complement of `0x36h`. |
| **`0x38`** | MAP Locked | Locked/stored MAP value (updated when bit `0x79.4` is set). |
| **`0x39`** | TPS | Throttle Position Sensor reading. |
| **`0x3A`** | TPS (Backup) | Secondary or filtered TPS reading. |
| **`0x3B`** | RPM (8-bit) | Simplified 8-bit engine speed calculation. |
| **`0x3D`** | RPM Low Byte | Low byte read from OKI 6260 coprocessor register `0x2004h`. |
| **`0x3E`** | RPM High Byte / Status | High byte read from OKI 6260 coprocessor. |
| **`0x47`** | Limit RPM Low | Low byte of RPM used for rev limit checks (copied from `0x3Dh`). |
| **`0x48`** | Limit RPM High | High byte of RPM used for rev limit checks (copied from `0x3Eh`). |
| **`0x49`** | Prev RPM Low | Historical low byte of engine speed (previous loop). |
| **`0x50`** | Prev RPM High | Historical high byte of engine speed (previous loop). |
| **`0x51`** | Delta RPM Low | Rate of RPM change (low byte). Calculated as `0x47` - `0x49`. |
| **`0x52`** | Delta RPM High | Rate of RPM change. Bit `0x17h` indicates the sign (1 = negative). |
| **`0x53`** | VSS High | High byte of 16-bit Vehicle Speed Sensor counter. |
| **`0x54`** | VSS Low | Low byte of 16-bit Vehicle Speed Sensor counter. |
| **`0x6A`** | Fuel Trim Add | Primary short-term fuel trim adjustment. |
| **`0x6C`** | VSS (8-bit) | Simplified 8-bit vehicle speed value. |
| **`0x6F`** | O2 Fuel Bias | Closed-loop fueling correction factor based on O2 sensor. |
| **`0x70`** | O2 Fuel Bias (Filtered)| Smoothed/integrated closed-loop fuel bias. |
| **`0xA2`** | Fuel Mult Low | Low byte multiplier used to adjust fuel injector pulse width. |
| **`0xA3`** | Fuel Mult High | High byte multiplier used to adjust fuel injector pulse width. |

## Internal RAM Bit Flags (Bit-Addressable)

Below are critical diagnostic and logic bits located in the bit-addressable internal RAM space:

| Bit Address | Flag Name | Technical Note / Threshold |
| :---: | :--- | :--- |
| **`0x60h`** | MAP CEL Flag | Set to 1 when the manifold pressure is out of normal operational bounds. |
| **`0x17h`** | RPM Delta Sign | Sign bit for engine acceleration (0 = accelerating, 1 = decelerating). |
| **`0x2Eh`** | RPM Limit Safe | Set to 1 when current engine speed is below the active rev limit. |
| **`0x57.0`** | Ignition Coil 1 | Firing indicator for coil phase 1. |
| **`0x57.1`** | Ignition Coil 2 | Firing indicator for coil phase 2. |
| **`0x71.1`** | Idle Threshold | Set to 1 if RPM is between ~890 and ~950 RPM (idle target zone). |
| **`0x71.2`** | VTEC RPM Cross | Set to 1 if RPM exceeds ~5,400 to ~5,600 RPM. |
| **`0x71.3`** | Decel Vacuum | Set to 1 if MAP is high-vacuum (~9.3 to ~8.7 in Hg / low load). |
| **`0x71.4`** | Medium Vacuum | Set to 1 if MAP is mid-vacuum (~6.0 to ~5.0 in Hg). |
| **`0x79.4`** | Mid-RPM threshold | Set to 1 if RPM is ~3400 to ~3650 RPM. Uses locked MAP `0x38h` if set. |
| **`0x79.6`** | Low Load Threshold | Set to 1 if MAP is ~6.0 to ~4.0 in Hg. |
| **`0x7A.4`** | High Load Threshold| Set to 1 if MAP is ~8.1 to ~6.0 in Hg. |

## External RAM (XRAM) Locations

These addresses exist in the external static RAM chip (typically a standard 5128 SRAM chip mapped via the `MOVX` command):

| XRAM Address | Parameter / Short Name | Notes & Functions |
| :---: | :--- | :--- |
| **`0x012h`** | VSS High Buffer | Temporarily holds the VSS high byte read from the OKI 6260 coprocessor. |
| **`0x013h`** | VSS Low Buffer | Temporarily holds the VSS low byte read from the OKI 6260 coprocessor. |
| **`0x032.2`** | Cranking Speed Flag | Set to 1 if engine speed is in the starting range (~540 to ~630 RPM). |
| **`0x032.3`** | High Load Fuel Cut | Set to 1 if MAP is extremely high pressure (~2.5 to ~1.0 in Hg). |
| **`0x07Dh`** | ADC Destination PTR | Address pointer specifying where the raw ADC byte from `0x4001h` is written. |
| **`0x0A1h`** | Checksum Accumulator| Holds the running checksum tally during ROM verification routines. |
| **`0x0A2h`** | Checksum Pointer | Holds the next high address byte (DPH) during ROM checksum loops. |

> [!IMPORTANT]
> When modifying these memory locations via custom code, ensure that the CPU interrupt flags are disabled to prevent race conditions during multi-byte reads of RPM or VSS data.