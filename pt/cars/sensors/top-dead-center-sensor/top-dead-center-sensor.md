---
summary: 'Technical overview of the Top Dead Center (TDC) sensor, including its location within the distributor and signal output characteristics for Honda OBD systems.'
tags: [sensors, ignition, diagnostics, distributor]
applies_to:
  models: [CRX, Civic, Integra]
complexity: beginner
---

# Top Dead Center (TDC) Sensor Technical Reference

The Top Dead Center (TDC) sensor is an electromagnetic sensor located within the distributor housing. It is a critical component for engine timing and fuel injection synchronization.

## Operation
The sensor utilizes a 4-tooth reluctor wheel mounted to the camshaft. As the camshaft rotates, the sensor generates an electromagnetic pulse for each tooth, resulting in 4 pulses per complete camshaft revolution.

> [!NOTE]
> Because the camshaft rotates at half the speed of the crankshaft, these 4 pulses correspond to the firing interval of the engine's cylinders.

## Technical Specifications
*   **Sensor Type:** Electromagnetic (Variable Reluctance)
*   **Signal Output:** 4 pulses per camshaft revolution
*   **Location:** Internal to the distributor assembly
*   **Function:** Provides the ECU with a reference signal for cylinder position and engine speed (RPM)

## Troubleshooting
If the ECU fails to receive a signal from the TDC sensor, the engine will typically fail to start or exhibit severe ignition timing instability.

> [!WARNING]
> When inspecting the sensor, ensure the air gap between the sensor pickup and the reluctor wheel teeth is free of metallic debris, as this can cause signal interference or "noise" in the ECU input.

{{> sensor-testing-procedures }}
