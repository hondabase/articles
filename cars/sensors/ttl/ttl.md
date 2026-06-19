---
summary: 'Transistor-Transistor Logic (TTL) utilizes 0/+5V signaling levels for native serial communication between microcontrollers and peripheral devices.'
tags: [ecu, reference, sensors, electronics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Transistor-Transistor Logic (TTL) Reference

Transistor-Transistor Logic (TTL) is a digital logic family that uses 0V to +5V signaling levels to represent binary states. It is the standard communication method for microcontrollers (MCUs) to interface with sensors, programmers, and serial communication modules.

## Signal Characteristics

TTL signals operate based on specific voltage thresholds to define logic states:

*   **Logic Low (0):** Typically 0V to 0.8V.
*   **Logic High (1):** Typically 2.0V to 5.0V.

> [!IMPORTANT]
> TTL is not natively compatible with RS-232 voltage levels (which can range from -15V to +15V). Connecting RS-232 signals directly to a TTL-based MCU will cause permanent hardware damage. Always use a level shifter (e.g., MAX232) when interfacing with RS-232 devices.

## Common Applications

TTL is utilized throughout ECU hardware for the following functions:

*   **Serial Communication:** Data exchange between the MCU and external tuning hardware or datalogging interfaces.
*   **Sensor Interfacing:** Digital sensors that output a square wave signal based on TTL voltage levels.
*   **MCU Programming:** Communication between a programmer and the MCU's internal memory (e.g., flashing ROM).

{{> resistor-color-codes }}

## Troubleshooting TTL Signals

When diagnosing communication issues, verify signal integrity using an oscilloscope or logic analyzer:

1.  **Check Ground Reference:** Ensure the ground of the measuring device is common with the ECU ground.
2.  **Verify Voltage Levels:** Confirm that the "High" state reaches at least 2.0V and the "Low" state is below 0.8V.
3.  **Check for Noise:** Excessive electrical noise on the signal line can cause bit errors during serial transmission. Ensure shielded cabling is used for long runs.
