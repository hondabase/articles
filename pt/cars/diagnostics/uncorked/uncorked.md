---
summary: 'Learn how to remove the internal ECU MAP sensor division code to increase boost pressure resolution and enable reading up to 11psi.'
tags: [ecu, tuning, rom, sensors, diagnostics]
complexity: beginner
---

# Uncorking the ECU MAP Sensor Input

The factory ECU code divides the [MAP sensor](/cars/fueling/map-sensor) input signal by two. This limitation restricts the maximum pressure the [ECU](/cars/ecu/ecu) can register to half of the sensor's actual physical capacity. By removing this division routine, the ECU is "uncorked," allowing it to utilize the full range of the MAP sensor, effectively enabling the reading of boost pressures up to 11psi.

## Technical Overview

The stock firmware applies a bitwise shift or division operation to the analog-to-digital converter (ADC) value received from the MAP sensor. This is a hard-coded limitation intended to keep the engine management within naturally aspirated parameters.

> [!IMPORTANT]
> Modifying the ROM to remove this division requires corresponding adjustments to the fuel and ignition maps. Failure to rescale your maps after "uncorking" the sensor will result in an extremely lean condition under boost.

## Implementation

To unlock the full range, the division instruction must be identified and replaced with a NOP (No Operation) or a direct register move.

### Procedure
1. **Locate the Routine:** Search the ROM disassembly for the division operation (typically a `LSR` or `DIV` instruction) immediately following the MAP sensor ADC read routine.
2. **Modify the Code:** Replace the division instruction with a `NOP` or ensure the register is passed directly to the lookup table index without modification.
3. **Rescale Tables:** Update the fuel and ignition tables to account for the new pressure range. The ECU will now interpret the full voltage sweep of the sensor as the maximum load value.

> [!TIP]
> Always verify your changes using a real-time emulator or a datalogger to ensure the MAP signal correlates correctly with a mechanical boost gauge before attempting to drive under load.

## Compatibility
This modification is applicable to most standard OBD0, OBD1, and OBD2 Honda ECU architectures where the MAP sensor input is processed via the internal ADC. Ensure your specific ROM version supports the address offsets for the MAP scaling routine before applying patches.
