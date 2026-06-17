---
summary: 'Learn how to modify stock ECU code to remove the MAP sensor division limit, allowing the ECU to read boost pressures up to 11psi.'
tags: [ecu, tuning, rom, sensors, diagnostics, map-sensor]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Removing MAP Sensor Software Limits (Uncorking)

The stock Honda ECU code divides the MAP sensor input signal by two. This effectively caps the maximum manifold pressure the ECU can register at half of the sensor's physical capability. 

By modifying the ROM to remove this division instruction, the ECU can utilize the full range of the MAP sensor, allowing for accurate readings up to 11 psi of boost.

> [!IMPORTANT]
> This modification only addresses the software limitation within the ECU. Ensure your fuel and ignition maps are properly scaled to accommodate the increased pressure range to prevent engine damage.

## Technical Overview

The stock firmware contains a routine that performs a bitwise shift or division operation on the incoming analog-to-digital converter (ADC) value from the MAP sensor. 

*   **Stock Behavior:** The ECU divides the raw MAP signal by 2.
*   **Modified Behavior:** The division instruction is replaced with a NOP (No Operation) or removed, allowing the raw 0–5V signal to be mapped linearly across the full range of the sensor.

> [!TIP]
> After "uncorking" the sensor, you must recalibrate your fuel and ignition tables. The ECU will now see higher voltage values at the same boost levels compared to the stock configuration.

## Implementation Steps

1.  **Locate the MAP Routine:** Identify the specific memory address in your ROM where the MAP sensor ADC value is processed.
2.  **Modify the Instruction:** Replace the division instruction (typically an `ASR` or `LSR` operation in the assembly code) with a `NOP` instruction.
3.  **Verify Scaling:** Ensure that the MAP sensor scaling tables in your tuning software are updated to reflect the new range.
4.  **Flash and Test:** Write the modified ROM to the ECU and verify the MAP reading using a data logging tool while the engine is off (key on, engine off) and under load.