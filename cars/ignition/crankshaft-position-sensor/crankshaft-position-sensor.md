---
summary: 'Technical overview of the Crankshaft Position (CKP) sensor, its function in engine management, and its integration within Honda distributor assemblies.'
tags: [sensor, ignition, ckp, distributor, timing]
applies_to:
  models: [civic, crx, del-sol, integra, prelude, accord, s2000, nsx]
  chassis: [ef, eg, ek, da, dc2, bb, cb-cd, ap1, ap2, na1-na2]
complexity: beginner
---

# Crankshaft Position (CKP) Sensor Operation

The Crankshaft Position (CKP) sensor provides the ECU with critical data regarding engine RPM and crankshaft rotational position. The ECU utilizes this signal as the primary reference for calculating fuel injection pulse width and ignition timing. A consistent and accurate CKP signal is required for engine operation.

## Sensor Integration
In most Honda distributor-based ignition systems, the CKP, Cylinder Position (CYP), and Top-Dead-Center (TDC) sensors are integrated into a single housing. These sensors utilize magnetic reluctor wheels driven by the camshaft to generate signals.

*   **CKP Sensor:** Features a high-tooth-count reluctor wheel to provide high-resolution engine speed data.
*   **TDC Sensor:** Uses a low-tooth-count wheel to identify the piston position of cylinder #1.
*   **CYP Sensor:** Uses a single-tooth wheel to identify the specific cylinder firing sequence.

> [!IMPORTANT]
> Because these sensors are located inside the distributor, internal bearing failure or debris accumulation on the reluctor wheels can cause erratic signal output, leading to misfires or a "no-start" condition.

## Diagnostic Considerations

If the ECU fails to receive a valid signal from the CKP sensor, it will typically trigger a diagnostic trouble code and disable fuel and spark delivery to prevent engine damage.

::: widget error-codes :::

## Related Components
- [Cylinder Position (CYP) Sensor](/cars/sensors/cylinder-position-sensor)
- [ECU Sensor Overview](/cars/sensors/ecu-sensors)