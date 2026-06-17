---
summary: "Learn how to manually correct ECU checksum errors for OBD0 and OBD1 Honda ROMs by calculating and patching the 8-bit checksum value."
tags: [ecu, tuning, rom, diagnostics]
applies_to:
  obd: [0, 1]
complexity: intermediate
---

# Manual Checksum Correction for Honda OBD0/OBD1 ECUs

There are two primary methods to resolve a checksum error. The first involves modifying the ROM program code to disable or bypass the checksum routine entirely. The second method, detailed below, involves manually calculating and patching the checksum to satisfy the ECU's validation routine.

## Checksum Fundamentals

The checksum for all OBD0 and OBD1 Honda ROMs is an 8-bit value, ranging from 00 to FF (0–255). 

*   **OBD0:** Typically validates the 0000–4FFF memory range (e.g., PM6 ECU).
*   **OBD1:** Typically validates the entire ROM image.

> [!IMPORTANT]
> To successfully correct the checksum, you must perform an 8-bit checksum calculation on the specific memory range monitored by your ECU.

## Correction Procedure

To manually correct the checksum, follow these steps:

1.  **Calculate the Current Checksum:** Use a hex editor (such as WinHex) or a dedicated utility (e.g., `check8`) to calculate the 8-bit checksum of the ROM file within the ECU's target range.
2.  **Determine the Patch Value:** Subtract your calculated checksum from `FF` (hex).
    *   *Example:* If your calculated checksum is `A3`, the calculation is: `FF - A3 = 5C`.
3.  **Locate Free Space:** Identify a byte or a block of `FF` values within the ROM's unused memory area.
4.  **Apply the Patch:** Replace one of the `FF` bytes with the result of your calculation (`5C` in this example).

> [!TIP]
> Always verify the checksum calculation again after applying the patch to ensure the final result is `00` (or the expected validation value) for the entire range.

## Recommended Tools

*   **WinHex:** A universal hex editor capable of calculating 8-bit checksums.
*   **check8:** A command-line utility for calculating 8-bit checksums.