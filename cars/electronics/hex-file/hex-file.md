---
summary: 'A "hex" file is a file encoded in Intel Hex format. The Intel HEX file is an ASCII text file with lines of text that follow the Intel HEX file format.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
  - ecu
---

# Hex File

A "hex" file is a file encoded in Intel Hex format. The Intel HEX file is an ASCII text file with lines of text that follow the Intel HEX file format. `Each` line in an Intel HEX file contains one HEX record. These records are made up of hexadecimal numbers that represent machine language code and/or constant data. Intel HEX files are often used to transfer the program and data that would be stored in a [ROM](/cars/electronics/rom) or [EPROM](/cars/electronics/eprom). Most [EPROM](/cars/electronics/eprom) programmers or emulators can use Intel HEX files.
