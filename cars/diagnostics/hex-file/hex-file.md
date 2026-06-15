---
summary: 'A "hex" file is a file encoded in Intel Hex format. The Intel HEX file is an ASCII text file with lines of text that follow the Intel HEX file format.'
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Hex File'
    url: /pgmfi/wiki/library/hex-file
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Hex File

A "hex" file is a file encoded in Intel Hex format. The Intel HEX file is an ASCII text file with lines of text that follow the Intel HEX file format. `Each` line in an Intel HEX file contains one HEX record. These records are made up of hexadecimal numbers that represent machine language code and/or constant data. Intel HEX files are often used to transfer the program and data that would be stored in a [ROM](/cars/rom/rom) or [EPROM](/cars/rom/eprom). Most [EPROM](/cars/rom/eprom) programmers or emulators can use Intel HEX files.
