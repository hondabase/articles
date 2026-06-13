---
summary: 'Author: evo (61.88.2.177) Date: 030403 22:15 After much thought, ive decided to share my AirConditioner Cutoff routine.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - sensors
  - reference
  - diagnostics
  - ecu
---

# AC Cut Routine

Author: evo (61.88.2.177) Date: 03-04-03 22:15 After much thought, ive decided to share my Air-Conditioner Cutoff routine. This routine cuts out the a/c under a specified rpm OR TPS level. JBR off 11.2, 4320 ; Jump if A/C switch is Off J XXXX ; Hook Code located at XXXX LC A, 6D8D ; Load Target rpm
 CMP AC, A ; Compare Actual rpm to Target rpm
 JLT 6D8A ; Jump if Actual rpm < Target
 LCB A, 6D8F ; Load Target TPS
 CMPB 6F, A ; Compare Actual TPS to Target TPS
 JGT 6D8A ; Jump if Actual TPS > Target
 SB off 26.4
 J 430C
 J 432B ; Jump to Cut A/C
The Code is located around the 4300 offset in the P30 203
