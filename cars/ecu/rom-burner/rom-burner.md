---
summary: 'A technical guide to selecting and using EPROM and Flash ROM burners for programming 27C256 and SST 27SF256 memory chips in Honda ECUs.'
tags: [hardware, ecu, tuning, rom, programming]
applies_to:
  obd: [0, 1, 2]
  models: [integra, civic, prelude]
  chassis: [ef, eg, ek]
complexity: intermediate
---

# Guide to EPROM and Flash ROM Burners

A ROM burner (device programmer) is an electronic tool used to write compiled binary calibration files (`.bin`) from a computer onto memory chips. These chips are then inserted into the IC socket of a modified ECU to run custom maps. 

Because Honda OBD0 and OBD1 ECUs require 32 KB of program space, selecting a burner that supports 256-kilobit (256k) memory chips is essential.

## 1. Supported Chip Types

While many chips share a DIP-28 package, their writing and erasing procedures vary:

* **27C256 (EPROM):** Erasable Programmable Read-Only Memory. These are typically one-time programmable (OTP) unless you use windowed chips, which require a dedicated ultraviolet (UV) eraser box to clear before rewriting.
* **SST 27SF256 (Flash EPROM):** The industry standard for tuning. It can be electrically erased and rewritten in seconds by the burner software, eliminating the need for UV light.
* **AT29C256 (EEPROM):** Electrically Erasable PROM. Similar to the SST flash chip, but utilizes different write timing algorithms and voltages.

## 2. Programmer Hardware Options

| Programmer Model | Interface | Status | Notes |
| :--- | :---: | :--- | :--- |
| **XGecu TL866 / T48** | USB | **Modern Standard** | Current go-to for DIY tuners. Supports SST 27SF256 and 27C256 chips with high reliability. |
| **Moates BURN1 / BURN2** | USB | **Legacy** | Designed specifically for automotive tuning; integrates natively with tuning software. |
| **Willem Programmer** | Parallel/USB | **Legacy** | Inexpensive open-source style board. Parallel versions require a native LPT port. |
| **Pocket Programmer 2** | Parallel | **Legacy** | Historically bundled with early Hondata packages. |
| **Batronix USB** | USB | **Professional** | High-quality professional burner with robust software support. |
| **Xeltek SuperPro** | USB | **Professional** | High-end industrial programmers; reliable but high cost for hobbyists. |

## 3. Programming Procedures

> [!IMPORTANT]
> Always select the exact manufacturer and model prefix of your chip (e.g., `SST27SF256`) in your burner software. Applying the incorrect programming voltage (Vpp) can permanently damage the chip.

> [!TIP]
> Always enable the **Verify** function in your burner software after writing. This compares the chip's written contents byte-by-byte against the source `.bin` file to ensure data integrity.

### Best Practices
* **Clean Contacts:** Ensure the chip pins and the burner socket are free of oxidation or debris to prevent intermittent connection errors.
* **Software Updates:** Keep your burner software updated to ensure the latest device algorithms are available.
* **Checksum Validation:** Use your tuning software to verify the checksum of the `.bin` file before burning to ensure the file is not corrupted.