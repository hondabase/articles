---
summary: 'Technical definition and explanation of Top Dead Center (TDC) in Honda internal combustion engines, covering its role in ignition timing and valve synchronization.'
tags: [sensors, ignition, timing, engine-management]
applies_to:
  obd: [0, 1, 2]
  models: [all]
  chassis: [all]
complexity: beginner
---

# Top Dead Center (TDC) Reference

Top Dead Center (TDC) refers to the position of a piston when it is at its highest point within the cylinder during the combustion cycle. In Honda engine management systems, the TDC sensor is critical for the ECU to determine the precise position of the crankshaft and camshafts to calculate ignition timing and fuel injection events.

## Technical Overview

The TDC sensor provides the ECU with a reference signal indicating when the number one piston is at the top of its compression stroke. This signal is essential for:

*   **Ignition Timing:** Determining when to trigger the spark plug for optimal combustion.
*   **Fuel Injection:** Synchronizing the injection pulse with the intake valve opening.
*   **Cylinder Identification:** Working in conjunction with Crankshaft Position (CKP) and Cylinder Position (CYP) sensors to identify the firing order.

> [!IMPORTANT]
> Incorrect TDC sensor alignment or a faulty signal will result in improper ignition timing, leading to engine misfires, poor fuel economy, or potential internal engine damage due to detonation.

## Sensor Functionality

The TDC sensor typically utilizes a magnetic pickup (Hall effect or inductive) to detect a reference mark on the camshaft or crankshaft pulley. 

| Sensor Type | Signal Output | Primary Function |
| :--- | :--- | :--- |
| **TDC** | Pulse per cycle | Piston #1 position reference |
| **CKP** | High-frequency pulses | Crankshaft speed and position |
| **CYP** | Pulse per cycle | Cylinder identification |

## Diagnostic Procedures

If the ECU detects an issue with the TDC signal, it will typically trigger a Diagnostic Trouble Code (DTC).

::: widget error-codes :::

> [!TIP]
> When troubleshooting TDC-related codes, always inspect the sensor wiring harness for heat damage or shielding degradation before replacing the sensor itself, as these are common failure points in older chassis.

## Related References

{{> resistor-color-codes }}