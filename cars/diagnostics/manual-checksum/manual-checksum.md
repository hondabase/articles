---
summary: 'Learn how to manually calculate and correct 8-bit checksums for OBD0 and OBD1 Honda ECU ROM files to resolve checksum errors.'
tags: [ecu, tuning, rom, diagnostics, checksum]
applies_to:
  obd: [0, 1]
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
---

# Manual Checksum Correction for Honda ECUs

Checksum errors occur when the ECU detects a discrepancy between the stored checksum value and the calculated sum of the ROM data. There are two primary methods to resolve this: disabling the checksum routine via code modification or manually adjusting the ROM to satisfy the existing checksum routine.

## Checksum Fundamentals

The checksum in all OBD0 and OBD1 ROMs is 8-bit, resulting in a value range of 00–FF (hex). 

*   **OBD0:** Typically validates the range 0000–4FFF (e.g., PM6 ECU).
*   **OBD1:** Typically validates the entire ROM file.

> [!NOTE]
> To perform these calculations, use a hex editor such as WinHex or a dedicated utility like `check8`.

## Manual Correction Procedure

If you are not modifying the ECU code to disable the routine, follow these steps to force a valid checksum:

1.  **Calculate the current checksum:** Run your checksum utility over the specified ROM range.
2.  **Determine the offset:** Subtract your calculated checksum value from `FF` (hex).
    *   *Example:* If your calculated checksum is `A3`, the calculation is `FF - A3 = 5C`.
3.  **Locate unused space:** Identify a byte containing `FF` within the range monitored by the ECU. It is recommended to locate a block of `FF`s, as this typically indicates unused ROM space.
4.  **Apply the patch:** Replace the `FF` byte with the result from your calculation (e.g., `5C`).

> [!IMPORTANT]
> Ensure you are modifying a byte in an unused area of the ROM. Overwriting active code or data tables will cause the ECU to malfunction or fail to start.

## Verification
After modifying the byte, re-run the checksum utility over the entire range. The resulting checksum should now be `FF`, which is the standard expected value for a valid Honda ROM checksum.