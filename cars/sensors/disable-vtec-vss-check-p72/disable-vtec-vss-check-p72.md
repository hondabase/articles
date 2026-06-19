---
summary: 'Technical guide for disabling the 25mph Vehicle Speed Sensor (VSS) requirement for VTEC engagement on the OBD1 P72 ECU.'
tags: [ecu, vtec, vss, tuning, p72]
applies_to:
  ecus: [P72]
  models: [integra]
  chassis: [dc2]
complexity: advanced
---

# Disabling VTEC VSS Check on P72 ECU

To disable the 25mph Vehicle Speed Sensor (VSS) requirement for VTEC engagement on the P72 ECU, the specific memory address must be modified.

> [!WARNING]
> Modifying ECU calibration data can result in engine damage if performed incorrectly. Ensure you have a verified backup of your current ROM before applying these changes.

## VTEC VSS Check Logic
The VTEC engagement logic relies on a speed threshold check. By modifying the value at address `547Dh`, the VSS requirement can be bypassed.

### Memory Map Reference
The following table outlines the relevant instruction sequence for the VTEC VSS check routine:

| Address | Opcode | Instruction |
| :--- | :--- | :--- |
| 11FD | C5 22 09 | RB 22.1 |
| 1200 | CB 24 | SJ 1226 |
| 1202 | C5 22 19 | SB 22.1 |
| 1205 | C5 F3 C0 32 | CMPB F3, #32 |
| 1209 | CA 1B | JLT 1226 |
| 120B | C5 D9 C0 44 | CMPB D9, #44 |
| 120F | CD 15 | JGE 1226 |
| 1211 | 90 9D 7D 54 | LCB A, 547D |
| 1215 | CE 03 | JNE 121A |
| 1217 | D8 31 0C | JBR off 31.0, 1226 |
| 121A | DB 1E 03 | JBR off 1E.3, 1220 |
| 121D | ED 19 03 | JBS off 19.5, 1223 |
| 1220 | E9 31 0B | JBS off 31.1, 122E |
| 1223 | E9 27 0F | JBS off 27.1, 1235 |
| 1226 | C5 22 08 | RB 22.0 |
| 1229 | C4 27 0A | RB off 27.2 |
| 122C | CB 17 | SJ 1245 |

## Modification Procedure
To disable the check, set the value at memory address `547Dh` to `FF`.

> [!TIP]
> Setting the value to `FF` effectively masks the VSS input, allowing VTEC to engage regardless of vehicle speed, provided other engagement criteria (RPM, Oil Pressure, ECT) are met.
