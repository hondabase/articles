---
summary: 'Technical reference for the OBD0 Vehicle Speed Sensor (VSS) data, including RAM memory location, linearity, and conversion formulas.'
tags: [ecu, reference, sensors, diagnostics, vss]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 Vehicle Speed Sensor (VSS) Data Reference

The Vehicle Speed Sensor (VSS) data in OBD0 ECU systems is stored in RAM location `06Ch`. 

## Technical Specifications

The VSS signal is linear; however, the system has a maximum readable threshold of approximately 157 kph.

### Data Conversion
To convert the raw hexadecimal or decimal value from RAM location `06Ch` to kilometers per hour (kph), use the following linear approximation:

**Formula:**
`Speed (kph) = 0.6229x - 2.1385`

> [!NOTE]
> The variable **x** represents the decimal value retrieved from RAM address `06Ch`.

> [!IMPORTANT]
> The sensor data saturates at approximately 157 kph. Values exceeding this threshold will not be accurately represented by the ECU.