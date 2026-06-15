---
summary: 'In the 8051 architecture, "C" is the name of the carry bit. When an arithmetic operation overflows, the carry bit is set to keep track of this change.'
tags: [sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'C Carry Bit'
    url: /pgmfi/wiki/library/c-carry-bit
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# C Carry Bit

In the 8051 architecture, "C" is the name of the carry bit. When an arithmetic operation overflows, the carry bit is set to keep track of this change. This bit is also frequently used as a storage space for transferring bits. This goes for the Oki 66k architecture as well; the MB C, x and MB x, C instructions allow easy access to the carry flag.
