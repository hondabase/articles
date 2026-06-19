---
summary: 'An overview of ECU clock speed, its role in MCU timing, and its impact on serial communication and timer-based calculations.'
tags: [ecu, mcu, timing, clock, reference]
complexity: beginner
---

# ECU Clock Speed Reference

The clock speed refers to the frequency of the crystal oscillator that drives the MCU. This frequency is the fundamental reference for all time-based operations within the ECU.

## Technical Significance

The clock speed is critical for calculating values dependent on internal timers, including:

*   **Serial Communication:** Baud rate generation for data logging and real-time tuning.
*   **Fuel and Ignition Timing:** Precise calculation of injector pulse width and ignition dwell/advance.
*   **Sensor Sampling:** Frequency of Analog-to-Digital Converter (ADC) polling.

> [!IMPORTANT]
> Any modification to the crystal oscillator frequency requires a corresponding adjustment to the software constants (e.g., baud rate divisors and timer prescalers) to maintain correct operational timing.

## Common Clock Frequencies

| ECU Generation | Typical Crystal Frequency |
| :--- | :--- |
| OBD0 | 12.000 MHz |
| OBD1 | 12.000 MHz |
| OBD2 | 12.000 MHz |

> [!NOTE]
> While 12 MHz is the standard for most Honda ECUs, verify the specific crystal markings on your PCB before performing any diagnostic or tuning procedures involving timing-sensitive calculations.
