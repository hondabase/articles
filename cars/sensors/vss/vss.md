---
summary: 'Technical overview of the Honda Vehicle Speed Sensor (VSS), including signal characteristics, diagnostic procedures, and its role in engine management systems.'
tags: [sensors, vss, diagnostics, wiring]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Vehicle Speed Sensor (VSS) Technical Reference

The Vehicle Speed Sensor (VSS) provides a pulsed signal to the ECU, which is critical for calculating vehicle speed, managing idle control, and enabling VTEC engagement.

## Signal Characteristics

The VSS typically operates as a Hall-effect sensor that generates a square-wave signal. As the transmission output shaft rotates, the sensor interrupts a ground signal, creating pulses that the ECU interprets as speed.

*   **Signal Type:** Square wave (0V to 5V or 0V to 12V depending on ECU/chassis).
*   **Frequency:** Proportional to vehicle speed.
*   **ECU Input:** The signal is sent to the ECU to determine speed-dependent fuel maps and VTEC activation thresholds.

## Troubleshooting

If the speedometer is non-functional or the ECU reports a VSS-related error code, perform the following checks:

1.  **Check Power:** Ensure the sensor is receiving 12V ignition power.
2.  **Check Ground:** Verify the sensor has a solid chassis ground.
3.  **Check Signal Wire:** Use a multimeter or oscilloscope to verify the presence of a pulsed signal at the ECU pin while the vehicle is moving.

> [!WARNING]
> A faulty VSS can prevent VTEC from engaging. Always verify VSS functionality before troubleshooting VTEC solenoid or oil pressure issues.

> [!TIP]
> If the speedometer works but the ECU reports a VSS error, check the continuity of the signal wire between the sensor and the ECU input pin.

## Diagnostic Tools

Use the following tool to identify specific error codes related to speed sensor malfunctions:

::: widget error-codes :::

## Related Wiring

For specific pinout locations regarding the VSS signal input, refer to the ECU pinout documentation for your specific chassis.

{{> ecu-pinout-reference }}
