---
summary: 'An overview of the Cylinder Position (CYP) sensor function, location, and its critical role in sequential ignition timing for Honda engines.'
tags: [sensor, ignition, diagnostics, distributor, obd1]
applies_to:
  obd: [obd0, obd1]
  models: [crx, civic, integra]
  chassis: [ef, eg]
complexity: intermediate
---

# Cylinder Position (CYP) Sensor Technical Overview

The Cylinder Position (CYP) sensor is a critical component in Honda engine management, responsible for providing the ECU with the necessary data to determine the engine's firing order and initiate sequential ignition.

## Sensor Location and Configuration
The physical location of the CYP sensor varies depending on the engine architecture:

*   **SOHC Engines:** The CYP sensor is integrated within the distributor housing.
*   **DOHC Engines:** The CYP sensor is typically mounted externally on the exhaust camshaft housing.
*   **1991 CRX (Example):** The CYP sensor is located at the front of the distributor assembly.

## Technical Operation
The CYP sensor is a magnetic pickup sensor consisting of a coil and a ferrous trigger wheel. As the trigger wheel rotates, the ferrous material passing the coil induces a voltage pulse.

> [!IMPORTANT]
> The ECU uses the CYP signal to establish the base reference for sequential ignition. Once the signal from the CYP sensor is received, the ECU initiates the ignition sequence in the firing order of 1-3-4-2 (or 1-3-2-4 depending on the specific engine configuration).

## Diagnostics and Troubleshooting
When diagnosing ignition timing issues, it is important to distinguish between sensor failure and mechanical timing discrepancies.

> [!NOTE]
> Excessive ignition timing advance or retard may mimic the symptoms of a failing CYP sensor. Verify mechanical ignition timing before condemning the sensor.

### Failure Symptoms
If the CYP sensor fails or provides an erratic signal, the following symptoms typically occur:
*   Engine misfire or rough running.
*   Illumination of the Malfunction Indicator Lamp (MIL).
*   Inability of the ECU to maintain sequential ignition timing.

### Visual Reference
![CYP Sensor](cyp.bmp)
*Typical appearance of the CYP sensor assembly*