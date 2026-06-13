---
summary: 'In the 8051 architecture, "C" is the name of the carry bit. When an arithmetic operation overflows, the carry bit is set to keep track of this change.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - sensors
  - reference
---

# C Carry Bit

In the 8051 architecture, "C" is the name of the carry bit. When an arithmetic operation overflows, the carry bit is set to keep track of this change. This bit is also frequently used as a storage space for transferring bits. This goes for the Oki 66k architecture as well; the MB C, x and MB x, C instructions allow easy access to the carry flag.
