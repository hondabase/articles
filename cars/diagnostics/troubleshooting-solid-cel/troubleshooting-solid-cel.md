---
summary: 'Diagnose and resolve a solid Check Engine Light (CEL) on Honda OBD0 and OBD1 ECUs, typically caused by hardware failures or improper EPROM installation.'
tags: [ecu, diagnostics, troubleshooting, obd1, obd0]
applies_to:
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eh]
complexity: intermediate
---

# Troubleshooting a Solid CEL

A "solid" Check Engine Light (CEL/MIL) that remains illuminated immediately upon turning the ignition to the ON position—without the standard 2-second bulb check—indicates a critical hardware or low-level software failure. The ECU enters "limp mode," utilizing a backup processor, which typically results in rough engine operation, a restricted rev limit, or a no-start condition.

## Overview

During the power-on self-test, the ECU's main microcontroller (MCU) performs several low-level diagnostic checks. On OBD0 and OBD1 ECUs, these include:

*   Checking Special Function Registers (SFRs) of the MCU.
*   Verifying internal and external RAM integrity.
*   Calculating and verifying the program Checksum (CS).
*   Verifying Analog-to-Digital (A/D) converter operation.
*   Verifying the 6260 mapping chip (if equipped).

If any of these checks fail, the MCU halts execution and triggers a solid CEL. On chipped (socketed) ECUs, the vast majority of solid CELs are caused by:

1.  **Bad ROM/Program:** Corrupt ROM files, incorrect checksums, or faulty EPROM burning.
2.  **Improper Soldering:** Cold solder joints, solder bridges (shorts), or open circuits on the socket, the `74HC373` latch, or the `J1` jumper.

## Diagnostic Procedure

Follow these steps to isolate the cause of a solid CEL on a chipped OBD0 or OBD1 ECU.

### Step 1: Test with a Stock ROM

Rule out software issues before investigating hardware.

1.  Burn an unmodified, stock program matching your specific ECU hardware (e.g., a stock P06 bin for a P06 ECU).
2.  If the ECU is VTEC-converted, test with a stock non-VTEC program first to verify base functionality.
3.  Install the chip and power the ECU.
4.  Observe the CEL and fuel pump:
    *   **Normal Behavior:** The CEL illuminates, the fuel pump primes for 2 seconds, and both then turn off.
    *   **Result:** If the ECU functions normally with a stock program, your soldering is sound. The issue resides in the custom ROM (e.g., incorrect checksum or incompatible code base).

### Step 2: Perform the J1 Jumper Test (OBD1 Only)

If the solid CEL persists with a known good stock ROM, test the hardware bypass.

1.  Locate the **`J1` jumper** on the ECU board, which directs the ECU to read from the external EPROM instead of the internal ROM.
2.  De-solder or cut one leg of the `J1` jumper to disable the external chip socket.
3.  Power up the ECU.

> [!IMPORTANT]
> If the CEL clears after cutting `J1`, the ECU's internal circuitry is functional. The fault is confirmed to be in the external socket, the `74HC373` latch, or the associated solder joints. If the CEL remains solid, the ECU hardware itself may be damaged.

### Step 3: Inspect and Test Soldering

If the `J1` test isolates the issue to the socket area, perform a physical inspection:

1.  Clean the PCB around the socket and latch with isopropyl alcohol to remove flux residue.
2.  Inspect all solder joints under magnification for:
    *   **Cold joints:** Dull, grey, or cracked solder.
    *   **Solder bridges:** Unintended connections between adjacent pins.
    *   **Lack of penetration:** Solder that failed to flow through the via to the top side of the board.
3.  Use a digital multimeter in continuity mode to verify connections between the EPROM socket, latch, and MCU.

### Step 4: Check Decoupling Capacitors

If you have installed noise-filtering decoupling capacitors (e.g., `C91` and `C92` on JDM P30 ECUs), verify their specifications.

> [!CAUTION]
> Using decoupling capacitors with incorrect values (e.g., 0.1µF instead of the recommended 10pF) can pull down critical signals like PSEN or ALE, triggering a solid CEL.

## Related Resources

*   [Introduction to ECU Chipping](/cars/tuning/introduction-to-ecu-chipping)
*   [ECU Troubleshooting](/cars/diagnostics/ecu-troubleshooting)
*   ::: widget error-codes :::
