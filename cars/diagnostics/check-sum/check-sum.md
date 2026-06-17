---
summary: 'A checksum is a fundamental error-checking mechanism used in Honda OBD0 and OBD1 ECUs to verify ROM integrity by summing data values.'
tags: [hardware, ecu, tuning, rom, diagnostics]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eh]
complexity: beginner
---

# ECU ROM Checksum Calculation and Verification

A checksum is a basic form of error checking used to verify the integrity of data within a ROM. It is calculated by summing the values of the ROM data without carry or overflow checking.

## Technical Overview
Checksums vary in bit-depth (8-bit, 16-bit, 32-bit). Honda OBD0 and OBD1 ECUs utilize 8-bit checksums, ranging from 0 to 255 decimal (00–FF hex).

> [!NOTE]
> The ECU performs this calculation to ensure the ROM image has not been corrupted. If the calculated checksum does not match the expected value, the ECU may trigger a diagnostic trouble code or fail to operate.

## Manual Checksum Adjustment
When modifying a ROM, the checksum must be recalculated and updated to maintain compatibility. The following procedure outlines how to manually adjust the checksum using a hex editor.

### Prerequisites
*   Hex editing software (e.g., WinHex).
*   Windows Calculator (set to Scientific/Hex mode).

### Procedure
1.  **Calculate Current Hash:** Open the ROM file in your hex editor. Navigate to the **Tools** menu and select **Calculate Hash** (8-bit). Record the resulting value.
2.  **Determine Correction Value:** Use the Windows Calculator in Hex mode to perform the following calculation:
    *   `FF - [Current_Checksum] = [Correction_Value]`
3.  **Apply Correction:**
    *   Locate an unused memory address (typically toward the end of the ROM file) that contains a value of `FF`.
    *   Replace the `FF` at that location with your calculated `[Correction_Value]`.
    *   If no `FF` value is available at an unused address, use the existing value at that location (e.g., `00`) in your calculation (`00 - [Current_Checksum]`) and replace that value with the result.

> [!TIP]
> Always maintain a backup of the original ROM file before performing manual edits.

## Tools
*   **Check8:** A utility designed to calculate 8-bit checksums for binary files.
*   **Hex Editors:** Software such as WinHex is recommended for viewing and modifying raw ROM data.