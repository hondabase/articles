---
summary: 'Technical overview of the Engine Coolant Temperature (ECT) sensor in Honda engines, including its role in fueling, ignition timing, and cold start enrichment.'
tags: [sensors, reference, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Engine Coolant Temperature (ECT) Sensor Reference

The Engine Coolant Temperature (ECT) sensor is a thermistor (a resistor that changes resistance based on temperature) used by the ECU to monitor the thermal state of the engine. The ECU uses this data to calculate fuel enrichment, ignition timing, and idle speed control.

## Sensor Operation
The ECT sensor is a Negative Temperature Coefficient (NTC) thermistor. As the coolant temperature increases, the electrical resistance of the sensor decreases. The ECU provides a 5V reference signal to the sensor and measures the voltage drop across it to determine the engine temperature.

> [!IMPORTANT]
> A faulty ECT sensor or a high-resistance connection in the wiring harness can cause the ECU to perceive a "cold" engine, leading to excessive fuel consumption, fouled spark plugs, and poor idle quality.

## ECU Interaction
The ECU utilizes the ECT signal for the following primary functions:

*   **Cold Start Enrichment:** Increases fuel injector pulse width during cold starts to ensure stable combustion.
*   **Ignition Timing:** Adjusts ignition advance maps based on operating temperature.
*   **Idle Speed Control:** Increases idle RPM during warm-up cycles.
*   **Closed-Loop Transition:** Determines when the engine has reached sufficient operating temperature to enter closed-loop fuel control.

## Troubleshooting
If the ECU detects an out-of-range signal from the ECT sensor, it will trigger a diagnostic trouble code (DTC).

::: widget error-codes :::

## Resistance Specifications
Typical resistance values for a standard Honda ECT sensor:

| Temperature (°C) | Resistance (kΩ) |
| :--- | :--- |
| -20°C | 14.5 – 17.5 |
| 0°C | 5.0 – 6.5 |
| 20°C | 2.1 – 2.9 |
| 40°C | 1.0 – 1.3 |
| 80°C | 0.27 – 0.38 |

> [!TIP]
> When testing the sensor, measure resistance directly at the sensor pins. If the resistance is within specification at the sensor but not at the ECU connector, inspect the wiring harness for corrosion or breaks.

## Wiring and Pinout
The ECT sensor typically utilizes a two-wire connector:
1.  **Signal:** Connects to the ECU ECT input pin.
2.  **Ground:** Connects to the sensor ground (often shared with other sensors at the ECU).

{{> sensor-ground-reference }}
