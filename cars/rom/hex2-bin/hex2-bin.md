---
summary: 'Learn how to convert Intel HEX files to binary (BIN) format for ECU tuning and ROM programming using the hex2bin utility.'
tags: [tuning, rom, software, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Converting Intel HEX Files to Binary (BIN)

To prepare ROM files for ECU programming, it is often necessary to convert Intel HEX format files into raw binary (BIN) files. The `hex2bin` utility is the standard tool for this conversion.

## Overview
Intel HEX files contain ASCII-encoded data with address information, which must be stripped and converted into a raw binary image to be readable by most EPROM programmers and ECU tuning software.

## Conversion Procedure

1. **Download the Utility:** Obtain the `hex2bin` executable.
2. **Prepare the File:** Ensure your source file is in the standard Intel HEX format.
3. **Execute Conversion:** Run the utility via the command line to generate the `.bin` output file.

> [!TIP]
> Always verify the checksum of the resulting binary file against your original HEX file data to ensure the conversion process was successful and no data corruption occurred.

## Resources
* [Download hex2bin Utility](http://www.keil.com/download/files/hex2bin.zip)
* [Understanding HEX Files](/cars/diagnostics/hex-file)
* [Understanding BIN Files](/cars/rom/bin-file)