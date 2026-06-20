---
summary: 'A mass air flow (MAF) system measures intake air directly using a MAF sensor to calculate precise fuel injector pulse width for target air-fuel ratio control.'
tags: [ecu, reference, tuning, rom, sensors, maf, fuel-control]
applies_to:
  brand: Honda
complexity: intermediate
---

# Mass Air Flow (MAF) System

## Overview

A mass air flow (MAF) engine management system uses a MAF sensor positioned in the intake manifold or air intake tract to directly measure the mass of air entering the engine. Using this measurement and fuel injector size, the ECU calculates the required fuel injector pulse width to achieve the target air-fuel ratio (AFR). MAF systems typically employ target AFR lookup tables based on air flow, differing from Speed Density systems (common in Honda PGM-FI applications) which use volumetric efficiency tables combined with sensor inputs to estimate air flow without direct measurement.

## How MAF Differs from Speed Density

| Aspect | MAF System | Speed Density System |
|--------|-----------|---------------------|
| **Air Flow Measurement** | Direct measurement via MAF sensor | Estimated from rpm, manifold pressure, and temperature |
| **Sensor Requirements** | MAF sensor | MAP sensor, IAT sensor |
| **Lookup Tables** | Target AFR vs. air flow | Volumetric efficiency vs. rpm and load |
| **Fuel Calculation** | Direct mass flow to fuel command | Estimated air mass to fuel command |
| **Response Time** | Fast, direct feedback | Slightly delayed due to estimation |

## MAF Sensor Operation

### Sensor Type
Most MAF sensors in automotive applications use a **hot-wire** or **hot-film** design:

- **Hot-Wire:** A thin platinum wire is heated electrically and cooled by passing air. The ECU measures current required to maintain constant temperature.
- **Hot-Film:** Similar principle but uses a thin film resistor instead of a wire for greater durability.

### Signal Output
The MAF sensor outputs a **voltage signal** (typically 0–5V) proportional to mass air flow, which the ECU monitors and uses to calculate fuel delivery.

> [!IMPORTANT]
> MAF sensor calibration and cleanliness are critical. Contamination (oil vapor, carbon) reduces accuracy and causes lean or rich running conditions.

## ECU Control Strategy

### Fuel Calculation Process

1. **Read MAF Voltage** — ECU samples the analog voltage from the MAF sensor.
2. **Convert to Mass Flow** — Voltage is scaled to mass air flow (typically in grams per second or kg/hour) using calibrated conversion curves.
3. **Look Up Target AFR** — ECU retrieves target AFR from a table indexed by air flow rate.
4. **Calculate Injector Pulse Width** — Pulse width is determined by:
   ```
   Pulse Width = (Air Mass / Injector Flow Rate) × (Target AFR Correction Factor)
   ```
5. **Output Fuel Command** — The calculated pulse width is output to the fuel injectors.

> [!TIP]
> MAF-based systems respond quickly to changes in throttle input, making them responsive and smooth for tuning applications.

## Advantages

- **Precise fuel control** — Direct air mass measurement eliminates estimation errors.
- **Responsive** — Fast sensor feedback allows quick ECU adjustments.
- **Simple load determination** — Air flow directly represents engine load without complex manifold pressure interpretation.

## Disadvantages

- **Sensor sensitivity** — MAF sensors are easily contaminated by fuel vapor and engine blow-by oil.
- **Calibration dependence** — System accuracy relies on accurate sensor calibration data in the ECU.
- **Cost** — MAF sensors are more expensive than alternative speed-density components.

> [!CAUTION]
> A faulty or contaminated MAF sensor can cause severe driveability issues, including stalling, hesitation, and incorrect fuel delivery. Always verify MAF sensor health during diagnostics.

## MAF Sensor Wiring

Refer to [MAF Sensor Wiring Reference](/cars/wiring/maf-sensor) for detailed connector pinouts and signal wiring diagrams specific to your vehicle.

## Related Systems

- **Air-Fuel Ratio (AFR)** — Target and measured AFR concepts.
- **Speed Density** — Alternative air estimation method.
- **Volumetric Efficiency** — Lookup table principle used in speed-density systems.
- **ECU** — Primary controller using MAF data.
