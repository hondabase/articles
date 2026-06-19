---
summary: 'An overview of MCU clock speeds in Honda ECUs and their critical role in timing-dependent operations like serial communication.'
tags: [ecu, mcu, timing, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda ECU Clock Speed Reference

Clock speed refers to the frequency of the crystal oscillator driving the Microcontroller Unit (MCU). This frequency serves as the fundamental heartbeat for the ECU's internal operations.

## Technical Importance
The clock speed is the primary reference for all time-based calculations within the ECU firmware. Accurate clock speed data is essential for:

*   **Serial Communication:** Calculating baud rates for data logging and real-time tuning.
*   **Timer Interrupts:** Managing fuel injection pulse width and ignition timing events.
*   **Sensor Sampling:** Ensuring analog-to-digital conversion occurs at the correct intervals.

> [!IMPORTANT]
> If the crystal oscillator frequency is modified or if the incorrect clock speed is assumed during firmware development, all timing-dependent functions—including serial communication and engine management—will operate at incorrect speeds, leading to data corruption or engine failure.

## Common Clock Configurations

| ECU Series | Typical Oscillator Frequency | Primary Use Case |
| :--- | :--- | :--- |
| OBD0 | 8.00 MHz | Early PGM-FI systems |
| OBD1 | 12.00 MHz | Standard PGM-FI (e.g., P30, P72) |
| OBD2 | 16.00 MHz | Advanced OBD2 management |

> [!TIP]
> Always verify the physical markings on the crystal oscillator located on the ECU PCB before attempting to calculate baud rate divisors for custom serial communication interfaces.
