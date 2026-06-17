---
summary: "The atmospheric pressure sensor (also called barometric pressure or PA sensor) measures a narrow range of pressure centered around atmospheric pressure and adjusts fuel mixture for altitude and weather changes."
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - atmospheric-pressure
  - pa-sensor
---

# Atmospheric Pressure Sensor

## Overview

The atmospheric pressure sensor, also known as the **barometric pressure sensor** or **PA sensor**, measures a narrow range of pressure centered around atmospheric pressure. The ECU uses this sensor to adjust fuel mixture and compensate for variations in air density caused by altitude or weather conditions.

## Function

The atmospheric pressure sensor provides real-time barometric pressure data to the ECU, enabling:

- **Altitude compensation** — Adjusts air-fuel ratio for elevation changes
- **Weather compensation** — Accounts for pressure variations from weather patterns
- **Emissions optimization** — Maintains proper combustion efficiency across operating conditions

## Technical Specifications

| Parameter | Description |
|-----------|-------------|
| **Measurement Range** | Narrow band centered on atmospheric pressure |
| **Output Type** | Analog voltage or digital signal |
| **OBD Support** | OBD-0, OBD-1, OBD-2 |

> [!NOTE]
> The PA sensor operates within a limited pressure range, unlike manifold absolute pressure (MAP) sensors which measure boost conditions and vacuum.

## Location and Integration

The atmospheric pressure sensor is typically mounted on or near the ECU to measure ambient barometric conditions. Some implementations integrate the sensor directly into the ECU housing for improved accuracy and signal isolation.

## Related Components

- **Manifold Absolute Pressure (MAP) Sensor** — Measures intake manifold pressure for load calculation
- **Air Temperature Sensor** — Complements pressure data for air density compensation
- **ECU** — Receives and processes PA sensor signals for fuel mapping adjustments