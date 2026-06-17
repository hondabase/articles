---
summary: 'A technical reference collection of Oki 66K assembly language routines and code snippets for modifying Honda OBD1 and OBD2 ECU firmware.'
tags: [ecu, assembly, firmware, programming, oki-66k]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: advanced
---

# Oki 66K Assembly Language Routines for Honda ECUs

This document serves as a technical reference for Oki 66K assembly language routines utilized in Honda OBD1 and OBD2 ECU firmware modification.

## Overview
The Oki 66K architecture is the core processor for Honda's early electronic control units. Modifying firmware requires an understanding of specific subroutines for sensor data processing, fuel mapping, and ignition timing calculations.

> [!IMPORTANT]
> Modifying ECU firmware carries a risk of engine damage. Ensure all code changes are verified against a stock ROM before flashing to a vehicle.

## Common Assembly Routines

### Data Conversion
Routines for converting raw ADC (Analog-to-Digital Converter) values into human-readable units (e.g., Celsius, PSI, AFR).

| Routine Name | Function | Input Register | Output Register |
| :--- | :--- | :--- | :--- |
| `ADC_TO_TEMP` | Converts raw thermistor data | A | X |
| `MAP_SCALING` | Scales manifold pressure | A, B | X |

### Sensor Processing
Standardized routines for handling input signals from engine sensors.

*   **ECT (Engine Coolant Temp):** Reads the thermistor voltage and applies the lookup table offset.
*   **IAT (Intake Air Temp):** Similar to ECT, but utilizes a different scaling constant.
*   **TPS (Throttle Position Sensor):** Normalizes the 0-5V input to a 0-255 (8-bit) range for map indexing.

## Implementation Guidelines

When integrating new routines into existing firmware, adhere to the following:

1.  **Register Preservation:** Always push/pop registers to the stack if a routine modifies them to prevent corruption of the main loop.
2.  **Memory Alignment:** Ensure all subroutines are aligned to the appropriate memory boundaries as defined by the ECU's specific ROM map.
3.  **Execution Time:** Keep routines concise. Excessive cycle counts in interrupt-driven routines can cause timing drift in fuel injection pulses.

> [!TIP]
> Use the `{{> 66k-instruction-set }}` partial for a quick reference of valid opcodes and cycle counts when optimizing your code.

## Related Documentation
*   [OBD1 Civic/Integra Firmware Routines](/cars/rom/obd1-civ-teg-routines)
*   [ECU Memory Mapping Reference](/cars/rom/memory-mapping)