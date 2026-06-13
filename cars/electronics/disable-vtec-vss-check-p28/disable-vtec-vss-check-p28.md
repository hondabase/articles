---
summary: 'Author: Gimpy Accord Date: 081403 03:42 1286 C5 22 19 : SB 22.1 1289 C5 F3 C0 32 : CMPB F3, 32 128D CA 1B : JLT 12AA 128F C5 D9 C0 44 : CMPB D9, 44 1293...'
applies_to:
  obd: [0, 1, 2]
  ecus: [P28]
  brand: Honda
complexity: beginner
tags:
  - tuning
  - rom
  - sensors
  - reference
---

# Disable VTEC VSS Check P28

Author: Gimpy Accord Date: 08-14-03 03:42

- 1286- C5 22 19 : SB 22.1
- 1289- C5 F3 C0 32 : CMPB F3, #32
- 128D- CA 1B : JLT 12AA
- 128F- C5 D9 C0 44 : CMPB D9, #44
- 1293- CD 15 : JGE 12AA
- 1295- 90 9D FA 60 : LCB A, 60FA
- 1299- CE 03 : JNE 129E
- 129B- D8 31 0C : JBR off 31.0, 12AA
- 129E- DB 1E 03 : JBR off 1E.3, 12A4
- 12A1- ED 19 03 : JBS off 19.5, 12A7
- 12A4- E9 31 0B : JBS off 31.1, 12B2
- 12A7- E9 27 21 : JBS off 27.1, 12CB
- 12AA- C5 22 08 : RB 22.0
- 12AD- C4 27 0A : RB off 27.2
- 12B0- CB 29 : SJ 12DB

I realize this is an old thread, but for the p28 rom users like me (shrug) set 60FA to FF. Basiclaly insert the same comments where appropriate from doc's post... unless you're anal. This became a real issue on my accord. My VTEC xover is 3000rpm and its hard to get to 20mph by 3000rpm in my car :) So VTEC would enguage about 4000 in 1st gear.
