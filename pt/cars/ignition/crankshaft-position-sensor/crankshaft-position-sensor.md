yaml
---
summary: "The crankshaft position sensor (CKP) measures engine speed and crankshaft angle, providing essential timing reference signals to the ECU for fuel injection and ignition control."
tags:
  - crankshaft-position-sensor
  - ckp-sensor
  - engine-speed
  - timing-reference
  - ignition-timing
  - fuel-injection
applies_to:
  obd: []
  models: []
  chassis: []
complexity: intermediate
---

# Crankshaft Position Sensor (CKP)

## Overview

The crankshaft position sensor (CKP) provides the ECU with critical information about engine speed and crankshaft rotational position. The ECU uses this signal as the primary timing reference for both fuel injection and ignition control, making a reliable CKP signal essential for engine operation.

> [!IMPORTANT]
> The engine will not run without a valid CKP signal. Sensor malfunction or signal loss immediately disables fuel injection and ignition.

## Sensor Architecture

In many older Honda models, the CKP, cylinder position (CYP), and top dead center (TDC) sensors are housed together within the distributor. All three sensors read from toothed reluctor wheels (tone wheels) driven by the camshaft.

### Reluctor Wheel Configuration

| Sensor | Wheel | Tooth Count | Purpose |
|--------|-------|-------------|---------|
| CKP | Crankshaft | High (many teeth) | Precise engine speed resolution |
| CYP | Cylinder | Low (few teeth) | Cylinder identification |
| TDC | Top Dead Center | Low (few teeth) | Cylinder position reference |

> [!NOTE]
> The high tooth count on the CKP reluctor wheel enables precise speed measurement and smooth timing calculations across all engine speeds.

## Related Articles

- [Cylinder Position Sensor (CYP)](/cars/sensors/cylinder-position-sensor)
- [ECU Sensors](/cars/sensors/ecu-sensors)