---
summary: 'An overview of the Intel HEX file format, an ASCII-based standard used for storing machine language code and data for ECU ROM and EPROM programming.'
tags: [tuning, rom, eprom, ecu, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Intel HEX File Format Overview

An Intel HEX file is an ASCII text file used to represent machine language code and constant data. Each line in the file constitutes a single HEX record, consisting of hexadecimal values that define the binary data to be programmed into a device.

These files are the standard format for transferring firmware and calibration data to be stored in ROM or EPROM chips. Most EPROM programmers and ECU emulators natively support the Intel HEX format for data ingestion.

## Record Structure

Each record in an Intel HEX file follows a specific structure to ensure data integrity and correct memory addressing:

* **Start Code:** Every line begins with a colon (`:`).
* **Byte Count:** Indicates the number of data bytes in the record.
* **Address:** Specifies the 16-bit starting memory address for the data.
* **Record Type:** Defines the type of data (e.g., data record, end-of-file record, extended segment address).
* **Data:** The actual machine code or constant data bytes.
* **Checksum:** A two-digit hexadecimal value used to verify the integrity of the record.

> [!NOTE]
> While Intel HEX is the industry standard for ECU programming, ensure your specific programmer or emulator software is configured to the correct memory offset if the file contains non-contiguous data blocks.

## Common Applications

* **ECU Flashing:** Transferring compiled binary maps to the ECU's memory.
* **EPROM Burning:** Programming physical chips for socketed ECUs.
* **Real-time Emulation:** Loading calibration data into hardware emulators for live tuning.
