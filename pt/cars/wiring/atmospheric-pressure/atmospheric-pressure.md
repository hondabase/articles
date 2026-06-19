---
summary: 'Atmospheric pressure is the gaseous pressure of air, approximately 14.7 psi, 1 bar, or 100 kPa at sea level. Pressure decreases with increasing altitude.'
tags: [atmospheric-pressure, pressure-measurement, sensor-calibration, diagnostics]
complexity: beginner
---

# Atmospheric Pressure

## Overview

Atmospheric pressure refers to the gaseous pressure exerted by the air at a given altitude. At sea level, standard atmospheric pressure is approximately **14.7 psi**, **1 bar**, or **100 kPa**. Pressure decreases progressively with increasing altitude above sea level.

> [!IMPORTANT]
> Atmospheric pressure is not constant and varies with altitude and weather conditions. This variation directly affects engine performance calculations and sensor readings.

## Pressure Units Reference

| Unit | Sea Level Value |
|------|-----------------|
| PSI (pounds per square inch) | 14.7 |
| Bar | 1.0 |
| kPa (kilopascals) | 100 |
| atm (atmospheres) | 1.0 |

## Altitude and Pressure Relationship

Atmospheric pressure decreases approximately exponentially with altitude. Common reference points:

- **Sea Level (0 m):** 14.7 psi / 101.3 kPa
- **1,000 m (3,281 ft):** ~11.9 psi / 82 kPa
- **2,000 m (6,562 ft):** ~9.7 psi / 67 kPa
- **3,000 m (9,843 ft):** ~7.9 psi / 54 kPa

## Impact on Engine Systems

Atmospheric pressure affects:

- **Air density** — Lower pressure means thinner air and reduced oxygen availability
- **Sensor calibration** — MAP (Manifold Absolute Pressure) and barometric pressure sensors depend on accurate atmospheric reference
- **Fuel mapping** — ECU calculations for air/fuel ratio compensation require accurate pressure input
- **Knock detection** — Atmospheric conditions influence combustion characteristics

> [!TIP]
> For accurate diagnostics and tuning, establish baseline atmospheric pressure readings at your specific location and altitude before making ECU adjustments.

## Pressure Unit Conversion

For quick reference conversions between common pressure units:

- **1 bar** = 14.5038 psi
- **1 psi** = 0.0689476 bar
- **1 bar** = 100 kPa
- **1 psi** = 6.89476 kPa
