---
summary: 'Technical guide on bypassing the Vehicle Speed Sensor (VSS) check within the VTEC routine for OBD1 P30 ROMs.'
tags: [tuning, rom, sensors, diagnostics, ecu, vtec, vss]
applies_to:
  ecus: [P30]
  models: [civic, del-sol]
  chassis: [ef, eg, eh]
complexity: advanced
---

# Disabling VTEC VSS Check on P30 ROMs

To bypass the Vehicle Speed Sensor (VSS) check in the VTEC routine for 203 or 209 ROMs, modify the hex value at memory address `6010` from `00` to `FF`.

> [!IMPORTANT]
> If using a ROM other than the 203 or 209, the memory address for the VSS check may differ. You must perform a disassembly to locate the specific routine.

## Locating the VTEC Routine

To identify the correct address for other ROM versions, disassemble the binary and search for the VTEC routine. Look for the standard bit reset/set instructions (`RB 22.1` and `RB 22.0`), which are consistent across most ROMs.

### Example Disassembly

| Address | Opcode | Instruction | Note |
| :--- | :--- | :--- | :--- |
| 11B9 | C5 22 09 | RB 22.1 | Reset Bit Port1.1 (VTEC) |
| 11BC | CB 24 | SJ 11E2 | Disable VTEC |
| 11BE | C5 22 19 | SB 22.1 | Set Bit Port1.1 |
| 11C1 | C5 E9 C0 32 | CMPB E9, #32 | |
| 11C5 | CA 1B | JLT 11E2 | |
| 11C7 | C5 C1 C0 44 | CMPB C1, #44 | |
| 11CB | CD 15 | JGE 11E2 | |
| 11CD | 90 9D 10 60 | LCB A, 6010 | **VSS Check** |
| 11D1 | CE 03 | JNE 11D6 | |
| 11D3 | D8 28 0C | JBR off 28.0, 11E2 | VSS Speed Check |

## Patching Procedure

The VTEC routine evaluates the VSS status using the following logic:

1.  **11CD:** Loads the ROM content at address `6010` into the accumulator.
2.  **11D1:** If the content is not `00`, the routine jumps to `11D6` (bypassing the speed check).
3.  **11D3:** If the bit `28.0` is `0`, the routine jumps to `11E2` (disabling VTEC).

### Recommended Methods

*   **Memory Patch:** Change the value at ROM address `6010` from `00` to `FF`.
*   **Instruction Patch:** Modify the jump instruction at `11CD` to force a jump to `11D6`.
*   **NOP Patch:** Replace the instruction at `11D3` with `NOP` (No Operation) instructions to prevent the VTEC disable jump.

> [!CAUTION]
> Always verify the disassembly of your specific ROM version before applying patches. Incorrect modifications can lead to unexpected ECU behavior or failure to engage VTEC.
