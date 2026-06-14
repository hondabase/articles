---
summary: 'How to diagnose a solid Check Engine Light (CEL/MIL) on Honda OBD0/OBD1 ECUs, which usually indicates limp mode or a bad ROM/connection.'
applies_to:
  obd: [0, 1]
complexity: intermediate
tags:
  - ecu
  - diagnostics
  - troubleshooting
---

# Troubleshooting a Solid CEL

A "solid" Check Engine Light (CEL/MIL) that turns on and stays on immediately when you turn the key to the ON position (without clicking off after 2 seconds) indicates a serious hardware or low-level software failure. When this happens, the ECU enters "limp mode" (running on a backup processor), which typically causes the engine to run very rough, have a low rev limit, or refuse to start.

## Overview

During its power-on self-test, the ECU's main microcontroller (MCU) performs several low-level checks. On an OBD0 or OBD1 ECU, these include:
*   Checking Special Function Registers (SFRs) of the MCU.
*   Verifying internal and external RAM integrity.
*   Calculating and verifying the program Checksum (CS).
*   Verifying Analog-to-Digital (A/D) converter operation.
*   Verifying the 6260 mapping chip (if equipped).

If any of these low-level hardware or software checks fail, the MCU halts execution and turns on the solid CEL. On chipped (socketed) ECUs, **95% of solid CELs are caused by one of two issues**:
1.  **Bad ROM/Program:** A corrupt ROM file, bad checksum, or a bad write/burn to the EPROM chip.
2.  **Improper Soldering:** Cold solder joints, solder bridges (shorts), or open circuits on the newly installed socket, latch (`74HC373`), or `J1` jumper.

## Procedure

Follow these step-by-step instructions to isolate and fix the cause of a solid CEL on a chipped OBD0 or OBD1 ECU.

### Step 1: Test with a Stock ROM
Rule out software issues first.
1.  Burn an unmodified, stock program for your specific ECU type (e.g., a stock P06 bin for a P06 ECU, or a stock P72 bin for a P72 ECU).
2.  *If the ECU is VTEC-converted:* Try a stock program for the original non-VTEC hardware configuration first, then a stock P28 program.
3.  Install the chip and power the ECU (either in the car or on a bench).
4.  Watch the CEL and listen to the fuel pump:
    *   **Normal Behavior:** The CEL should turn on, the fuel pump should prime the fuel rail for 2 seconds, and then both the CEL and fuel pump should turn off.
    *   **Result:** If the ECU behaves normally with a stock program, your soldering is fine. The problem lies with the custom ROM you were trying to use (e.g., incorrect checksum, incompatible code base, or corrupt bin file).

### Step 2: Perform the `J1` Jumper Test (OBD1 Only)
If the ECU still shows a solid CEL with a known good stock ROM, test the hardware bypass.
1.  Locate the **`J1` jumper** on the ECU board (which tells the ECU to read from the external EPROM chip instead of its internal ROM).
2.  De-solder or cut one leg of the `J1` jumper. This disables the external chip socket and reverts the ECU to its factory internal ROM.
3.  Power up the ECU.
    *   **Result A (Normal operation):** If the solid CEL goes away, the ECU's internal circuitry is fine. The issue is definitely located in your external chip socket, the `74HC373` latch chip, or the solder joints connecting them.
    *   **Result B (Solid CEL persists):** If the CEL remains solid even with `J1` cut, the ECU itself is likely damaged (fried) and may need to be replaced.

### Step 3: Inspect and Test Soldering
If the `J1` test proved the external socket area is the problem, inspect the board.
1.  Clean the top and bottom of the PCB around the socket and latch using isopropyl rubbing alcohol and a toothbrush to remove all flux residue.
2.  Use a magnifying glass or jeweler's loupe under bright light to inspect every solder joint on the EPROM socket, the `74HC373` latch, and `J1`. Look for:
    *   **Cold joints:** Dull, grey, or cracked solder that didn't flow correctly.
    *   **Solder bridges:** Tiny blobs of solder bridging two adjacent pins.
    *   **Lack of penetration:** Solder that did not flow all the way through the via to the top side of the board.
3.  Use a digital multimeter in continuity mode to trace connections between the EPROM socket, latch, and MCU to ensure there are no open circuits or shorted pins.

### Step 4: Check decoupling capacitors
If you added noise-filtering decoupling capacitors (e.g., `C91` and `C92` on JDM P30 ECUs):
*   Verify their capacitance. Using decoupling capacitors that are too large (e.g., 0.1µF instead of the recommended 0.00001µF / 10pF) can pull down signals like PSEN or ALE, triggering a solid CEL.

## Related

*   [Introduction to ECU Chipping](/cars/electronics/introduction-to-ecu-chipping)
*   [ECU Troubleshooting](/cars/electronics/ecu-troubleshooting)
*   [ECU Trouble Codes](/cars/electronics/ecu-trouble-codes)
