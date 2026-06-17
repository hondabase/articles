---
summary: 'Technical overview of the Honda Top Dead Center (TDC) sensor, including its location within the distributor and signal output characteristics.'
tags: [sensors, ignition, distributor, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [CRX, Civic, Integra]
  chassis: [EF, EG, DC]
complexity: beginner
---

# Top Dead Center (TDC) Sensor Technical Reference

The Top Dead Center (TDC) sensor is a magnetic pickup located within the distributor housing. It provides the ECU with precise crankshaft position data relative to the camshaft rotation.

## Operation
The sensor utilizes a reluctor wheel with four teeth. As the distributor shaft rotates, the teeth pass the magnetic sensor, generating an electromagnetic pulse.

*   **Signal Output:** 4 pulses per 1 camshaft revolution.
*   **Sensor Type:** Magnetic inductive pickup.
*   **Location:** Integrated inside the distributor assembly.

> [!NOTE]
> Because the distributor rotates at half the speed of the crankshaft, the 4 pulses per camshaft revolution correspond to 8 pulses per crankshaft revolution.

## Diagnostic Specifications

| Parameter | Specification |
| :--- | :--- |
| **Signal Type** | AC Voltage (Sine Wave) |
| **Pulse Count** | 4 pulses / camshaft rev |
| **Component Location** | Internal Distributor |

> [!WARNING]
> Ensure the distributor cap is removed and the ignition is switched off before attempting to inspect or test the sensor wiring to prevent electrical shock or damage to the ignition coil.

## Troubleshooting
If the ECU fails to receive a signal from the TDC sensor, it will typically trigger a diagnostic trouble code (DTC) related to the ignition system or crankshaft position.

::: widget error-codes :::

{{> sensor-testing-procedures }}