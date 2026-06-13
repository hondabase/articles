---
summary: "How to disable 25mph VSS check for VTEC engagement on P72: Author: Speedz Date: 082303 15:59 here's where its at in the p72 :) 11FD C5 22 09 : RB 22."
applies_to:
  obd: [0, 1, 2]
  ecus: [P72]
complexity: beginner
tags:
  - sensors
  - reference
---

# Disable VTEC VSS Check P72

How to disable 25mph [VSS](/cars/electronics/vss) check for VTEC engagement on P72: Author: Speedz Date: 08-23-03 15:59 here's where its at in the p72 :)

- 11FD- C5 22 09 : RB 22.1
- 1200- CB 24 : SJ 1226
- 1202- C5 22 19 : SB 22.1
- 1205- C5 F3 C0 32 : CMPB F3, #32
- 1209- CA 1B : JLT 1226
- 120B- C5 D9 C0 44 : CMPB D9, #44
- 120F- CD 15 : JGE 1226
- 1211- 90 9D 7D 54 : LCB A, 547D
- 1215- CE 03 : JNE 121A
- 1217- D8 31 0C : JBR off 31.0, 1226
- 121A- DB 1E 03 : JBR off 1E.3, 1220
- 121D- ED 19 03 : JBS off 19.5, 1223
- 1220- E9 31 0B : JBS off 31.1, 122E
- 1223- E9 27 0F : JBS off 27.1, 1235
- 1226- C5 22 08 : RB 22.0
- 1229- C4 27 0A : RB off 27.2
- 122C- CB 17 : SJ 1245

looks like 547Dh is the spot :) (disable = FF)
