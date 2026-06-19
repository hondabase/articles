---
summary: 'Technical overview of the Intake Air Temperature (IAT) sensor and its critical role in air density calculations and fueling corrections for Honda ECUs.'
tags: [sensors, reference, iat]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Intake Air Temperature (IAT) Sensor Reference

The Intake Air Temperature (IAT) sensor is a thermistor used by the Engine Control Unit (ECU) to measure the temperature of the air entering the intake manifold. This data is critical for calculating air density, which allows the ECU to apply necessary fueling corrections based on ambient conditions.

## Operation
The IAT sensor functions as a negative temperature coefficient (NTC) thermistor. As the intake air temperature increases, the electrical resistance of the sensor decreases. The ECU monitors the voltage drop across the sensor to determine the temperature.

> [!IMPORTANT]
> Accurate IAT readings are essential for proper ignition timing and fuel trim calculations. Heat soak, where the sensor absorbs heat from the intake manifold, can lead to artificially high temperature readings and subsequent timing retard or fuel enrichment.

## Technical Specifications
The sensor is typically wired in a voltage divider circuit with a pull-up resistor located inside the ECU.

| Temperature (°C) | Resistance (kΩ) |
| :--- | :--- |
| -20 | 14.0 – 17.0 |
| 0 | 5.0 – 6.5 |
| 20 | 2.0 – 3.0 |
| 40 | 1.0 – 1.5 |
| 80 | 0.25 – 0.35 |

## Diagnostics
If the ECU detects an open or short circuit in the IAT sensor wiring, it will trigger a diagnostic trouble code and revert to a default lookup table based on coolant temperature or a fixed value.

::: widget error-codes :::

## Related Components
* **ECT Sensor:** The Engine Coolant Temperature sensor works in tandem with the IAT to determine overall engine thermal state.
* **MAP Sensor:** The Manifold Absolute Pressure sensor provides the load signal, which is corrected by the IAT density calculation.

{{> resistor-color-codes }}
