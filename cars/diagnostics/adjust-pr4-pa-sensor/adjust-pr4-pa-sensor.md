---
summary: 'Technical guide for identifying and configuring internal versus external atmospheric pressure (PA) sensors on PR4 ECUs.'
tags: [ecu, tuning, sensors, diagnostics, pr4]
applies_to:
  models: [integra]
  chassis: [da, dc2]
complexity: intermediate
---

# PR4 ECU Atmospheric Pressure (PA) Sensor Configuration

The PR4 ECU utilizes either an internal or external atmospheric pressure (PA) sensor depending on the production year and specific ECU variant. Generally, 1990 PR4 ECUs utilize an external PA sensor, while 1991 PR4 ECUs utilize an internal PA sensor.

## ECU Variant Identification

The following table outlines the PR4 ECU variants and their associated programming:

| Label | Description |
| :--- | :--- |
| A00 | 1990 5-Speed (-33 program) |
| A01 | 1990 5-Speed |
| A02 | 1990 5-Speed (-54 program) |
| A51 | 1990 Automatic |
| A52 | 1990 Automatic (-54 program) |
| A10 | 1991 5-Speed (-92 program) |
| A12 | 1991 5-Speed (-92 program) |
| A60 | 1991 Automatic (-92 program) |
| A62 | 1991 Automatic (-92 program) |

## Sensor Configuration

To convert between internal and external PA sensor configurations, modify the following components on the ECU PCB:

| Part | External PA Configuration | Internal PA Configuration |
| :--- | :--- | :--- |
| PA Sensor | Missing | Installed |
| C103 | Missing | Present (103Z) |
| R92 | Jumper | 10K Ohm |
| C106 | Present | Missing |

> [!IMPORTANT]
> Verify the presence of C106 when performing these modifications. ECUs configured for an internal PA sensor typically require C106 to be removed, while those using an external sensor require it to be installed.
