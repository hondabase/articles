---
summary: 'A piezo-electric sensor that monitors engine block vibrations to detect detonation and allow the ECU to adjust ignition timing.'
tags: [knock, sensor, ignition, detonation, timing]
applies_to:
  engines: [B-Series, H-Series]
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eh, ek]
complexity: intermediate
---

# Knock Sensor Operation and Diagnostics

The knock sensor is a piezo-electric transducer bolted to the engine block that functions as a microphone, detecting the specific high-frequency vibrations associated with pre-ignition (detonation). The ECU processes this signal to retard ignition timing, preventing catastrophic engine damage.

## Application
Knock sensors are standard equipment on DOHC VTEC engines, including the B16, B18C, and H22 series, as well as most OBD2 SOHC VTEC engines.

## Technical Operation
The sensor generates a voltage signal proportional to the vibration frequency of the engine block. This signal is routed to a dedicated knock-detection circuit (often referred to as the "knock board") integrated into the ECU. 

*   **Signal Processing:** The ECU filters the input to isolate the specific frequency range characteristic of engine knock.
*   **Timing Correction:** Upon detecting knock, the ECU applies a pre-programmed ignition timing retard map to suppress detonation.

## Limitations in Forced Induction
The factory knock-detection system is calibrated for stock engine configurations and is generally considered insufficient for high-performance or forced-induction applications.

> [!WARNING]
> The factory knock board is prone to false positives when used with forged internal components, which have different acoustic properties than cast pistons. 

> [!TIP]
> For boosted applications, the factory sensor should be treated as a secondary safeguard against poor fuel quality. It is highly recommended to utilize a dedicated aftermarket knock-detection system for precise engine protection.

## Diagnostics and Reference
Use the following resources for troubleshooting and sensor calibration:

::: widget error-codes :::

*   **Voltage Reference:** [Knock Sensor Voltages](/cars/sensors/knock-sensor-voltages)
*   **Diagnostic Procedures:** [ECU Trouble Codes](/cars/diagnostics/diagnostic-trouble-codes)
