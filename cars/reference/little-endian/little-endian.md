---
summary: "Little Endian is the layout of multibyte values in memory used by many processors, including Intel x86's and OKI 66k's."
tags: [reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Little Endian'
    url: /pgmfi/wiki/library/little-endian
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Little Endian

Little Endian is the layout of multi-byte values in memory used by many processors, including Intel x86's and OKI 66k's. Little Endian layout stores the ***least significant byte first***. For 16-bit values, the actual value is Second Byte*256 + First Byte
