---
summary: 'Technical guide for disabling the Vehicle Speed Sensor (VSS) check in the VTEC engagement routine for Honda P28 OBD1 ECUs.'
tags: [tuning, sensors, vtec, p28]
applies_to:
  ecus: [P28]
  models: [accord, civic]
  chassis: [ef, eg]
complexity: intermediate
---

# Disabling VTEC VSS Check on P28 ECUs

The P28 ECU includes a factory safety routine that prevents VTEC engagement unless the vehicle has reached a minimum speed threshold. This can cause inconsistent VTEC crossover points in vehicles with short gearing or specific driving conditions where the engine reaches the crossover RPM before the vehicle reaches the required speed.

## VTEC VSS Bypass Procedure

To bypass the VSS check, modify the memory address `60FA` within the ECU ROM.

> [!IMPORTANT]
> Setting the value at `60FA` to `FF` effectively disables the speed requirement for VTEC engagement, allowing VTEC to engage based solely on RPM and load parameters.

## Assembly Reference

The following assembly code represents the VTEC engagement routine logic within the P28 firmware:

| Address | Opcode | Instruction | Note |
| :--- | :--- | :--- | :--- |
| 1286 | C5 22 19 | SB 22.1 | Set bit |
| 1289 | C5 F3 C0 32 | CMPB F3, #32 | Compare |
| 128D | CA 1B | JLT 12AA | Jump if less than |
| 128F | C5 D9 C0 44 | CMPB D9, #44 | Compare |
| 1293 | CD 15 | JGE 12AA | Jump if greater or equal |
| 1295 | 90 9D FA 60 | LCB A, 60FA | Load VSS threshold |
| 1299 | CE 03 | JNE 129E | Jump if not equal |
| 129B | D8 31 0C | JBR off 31.0, 12AA | Jump bit reset |
| 129E | DB 1E 03 | JBR off 1E.3, 12A4 | Jump bit reset |
| 12A1 | ED 19 03 | JBS off 19.5, 12A7 | Jump bit set |
| 12A4 | E9 31 0B | JBS off 31.1, 12B2 | Jump bit set |
| 12A7 | E9 27 21 | JBS off 27.1, 12CB | Jump bit set |
| 12AA | C5 22 08 | RB 22.0 | Reset bit |
| 12AD | C4 27 0A | RB off 27.2 | Reset bit |
| 12B0 | CB 29 | SJ 12DB | Short jump |

> [!TIP]
> This modification is particularly useful for vehicles with low-RPM VTEC crossover points where the vehicle speed threshold is not met during rapid acceleration in lower gears.
