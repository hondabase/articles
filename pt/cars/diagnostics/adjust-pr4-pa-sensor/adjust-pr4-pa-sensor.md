---
summary: 'Technical guide for identifying and configuring internal versus external Pressure Atmosphere (PA) sensors on PR4 ECUs.'
tags: [ecu, tuning, rom, sensors, diagnostics]
applies_to:
  ecus: [PR4]
complexity: intermediate
---

# PR4 ECU Pressure Atmosphere (PA) Sensor Configuration

The PR4 ECU configuration for the Pressure Atmosphere (PA) sensor varies based on the production year. Generally, 1990 PR4 ECUs utilize an external PA sensor, while 1991 PR4 ECUs utilize an internal PA sensor.

## ECU Identification
The following table outlines PR4 ECU variants and their associated programming codes:

| Label | Description |
| :--- | :--- |
| A00 | 1990 5-Speed (Program -33) |
| A01 | 1990 5-Speed |
| A02 | 1990 5-Speed (Program -54) |
| A51 | 1990 Automatic |
| A52 | 1990 Automatic (Program -54) |
| A10 | 1991 5-Speed (Program -92) |
| A12 | 1991 5-Speed (Program -92) |
| A60 | 1991 Automatic (Program -92) |
| A62 | 1991 Automatic (Program -92) |

## Sensor Configuration
To convert between internal and external PA sensor configurations, modify the PCB components according to the table below:

| Component | External PA | Internal PA |
| :--- | :--- | :--- |
| PA Sensor | Not Installed | Installed |
| C103 | Not Installed | Installed (103Z) |
| R92 | Jumper | 10K Ohm |
| C106 | Installed | Not Installed |

> [!NOTE]
> ECUs configured for an internal PA sensor typically omit capacitor C106, whereas ECUs configured for an external PA sensor require C106 to be present.
