---
summary: 'A command-line utility for verifying and correcting 8-bit ROM checksums during firmware compilation.'
tags: [tuning, rom, checksum, firmware]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# check8 8-Bit ROM Checksum Utility

**check8** is a command-line utility designed to verify and correct 8-bit checksum values in binary ROM files. It is primarily used during the firmware compilation and assembly process to ensure data integrity.

## Overview
The utility calculates the 8-bit checksum of a specified binary file and can automatically update the file to include the correct checksum value. This is essential when modifying ECU maps or custom firmware to prevent checksum-related errors during ECU initialization.

> [!IMPORTANT]
> Ensure the binary file is not currently in use by another process or emulator before running the utility to prevent file access errors.

## Usage
The utility is executed via the command line. Standard syntax typically requires the target filename as an argument:

`check8 <filename.bin>`

### Features
* **Verification:** Scans the binary file and compares the existing checksum against the calculated value.
* **Correction:** Automatically patches the binary file with the correct 8-bit checksum if a mismatch is detected.
* **Compatibility:** Compatible with standard binary ROM formats used in OBD-series ECU tuning.

## Availability
The utility is provided as part of the Keil compiler toolchain. It can be obtained through the official [Keil website](http://www.keil.com).