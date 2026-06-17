---
summary: 'Technical analysis of the Honda 6260A ECU diagnostic routine, detailing the memory-mapped LED trigger logic and procedures for signal mapping.'
tags: [ecu, diagnostics, firmware, 6260a]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Honda 6260A ECU Diagnostic LED Routine

The 6260A code routine manages the ECU diagnostic LED output. The ECU firmware triggers the Check Engine Light (CEL) by writing specific hexadecimal values to memory address `X2000` during diagnostic procedures.

## Diagnostic Logic
The firmware controls the diagnostic LED state through specific writes to the `X2000` memory register. The LED behavior is determined by the following values:

*   **Value #16:** Standard diagnostic flash sequence.
*   **Value #96:** Alternative diagnostic flash sequence (dependent on specific ECU state).

> [!TIP]
> Bench testing can be performed by modifying the firmware to write values other than #16 or #96 to `X2000`. This allows for the observation of other hardware lines that may toggle in response to these memory writes.

## Experimental Procedure
To identify additional output signals controlled by this routine, follow these steps:

1.  **Disassemble:** Locate the diagnostic routine within the ECU firmware.
2.  **Modify:** Replace the standard `MOV` instructions (writing #16 or #96) with custom values.
3.  **Monitor:** Use a logic analyzer or oscilloscope on the ECU output pins to detect signal toggling during the execution of the modified code.

::: widget error-codes :::