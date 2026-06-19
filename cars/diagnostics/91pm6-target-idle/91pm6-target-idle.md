---
summary: 'Technical analysis of the 1991 PM6 ECU target idle routine, including memory address locations and code structure comparisons with the PM7 ECU.'
tags: [tuning, rom, sensors, diagnostics, ecu, pm6]
applies_to:
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
---

# 1991 PM6 ECU Target Idle Routine Analysis

The target idle routine for the 1991 PM6 ECU is located at memory address `@279A`. The stock idle target is configured to 768 RPM.

## Memory Mapping
Idle settings are stored in a data table beginning at address `398F`. This table contains six distinct idle settings, which are selected based on engine load conditions, including the status of the Electrical Load Detector (ELD).

## Code Logic
The routine retrieves the idle value by moving the value at `x3995` to the data pointer. It then performs a conditional check on bit `26h.2`:

*   **If bit 26h.2 is set:** The routine proceeds to the next step.
*   **If bit 26h.2 is not set:** The routine moves the value at `x398F` into the data pointer and continues.

> [!NOTE]
> The values stored at `x3995` and `x398F` are identical in the stock PM6 ROM.

## Technical Context
The PM6 firmware is derived from the PM7 ECU. The redundancy observed in the idle routine—where two different memory addresses point to the same value—is a result of the PM6 inheriting the PM7 code structure without full optimization. 

> [!TIP]
> Similar legacy code artifacts exist elsewhere in the PM6 firmware, such as the speed limiter routine, which remains present in the code but is configured with an extremely high threshold to effectively disable it.
