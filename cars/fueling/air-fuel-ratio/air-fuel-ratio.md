---
summary: 'An introduction to Air-Fuel Ratio (AFR) in internal combustion engines, explaining stoichiometric targets, rich vs. lean conditions, and sensor scales.'
tags: [fueling, tuning, sensor]
applies_to:
  obd: [0, 1, 2]
  models: [integra]
  chassis: {}
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Air Fuel Ratio'
    url: /pgmfi/wiki/library/air-fuel-ratio
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Air-Fuel Ratio (AFR) Guide for Honda Tuning

Air-Fuel Ratio (AFR) is the mass ratio of air to fuel present in an engine's combustion chamber. It is one of the most critical variables in engine management, directly dictating combustion safety, thermal efficiency, exhaust emissions, and horsepower output. 

Understanding how to calibrate fuel maps to target specific AFRs is the foundation of custom Honda ECU tuning.

---

## 1. Stoichiometry, Rich, and Lean Mixtures

The behavior of the air-fuel mixture is classified relative to its stoichiometric point:

- **Stoichiometric Ratio (14.7:1 for gasoline):** The chemically ideal ratio where all oxygen and fuel are completely consumed during combustion. This is the target for cruising and idling, allowing the catalytic converter to clean exhaust gas with maximum efficiency.
- **Rich Mixture (AFR < 14.7):** Contains excess fuel. Rich mixtures burn cooler and slower, acting as a chemical cooling agent for the pistons and valves. Peak power on naturally aspirated gasoline engines is typically achieved in a slightly rich window between **12.8:1 and 13.2:1**.
- **Lean Mixture (AFR > 14.7):** Contains excess air. Lean mixtures burn hotter and faster. Cruising ranges can sometimes run slightly lean (up to 15.2:1) to maximize fuel economy, but running lean under heavy load will quickly cause detonation (knock) and melt pistons or exhaust valves.

---

## 2. Target AFR Guide by Load Zone

When tuning fuel lookup maps, aim for these target AFR values depending on engine load (manifold pressure) and RPM:

| Engine Type / Load Zone | Manifold Pressure | Target AFR Range | Tuning Objective |
| :--- | :--- | :---: | :--- |
| **Idle & Light Cruising** | High Vacuum (columns 1-5) | **14.7:1** | Closed-loop fuel economy and low emissions |
| **Naturally Aspirated WOT** | Atmospheric / 0 psi | **12.8:1 - 13.2:1** | Peak power torque output |
| **Forced Induction (Low Boost)** | 0 to 5 psi | **12.0:1 - 12.5:1** | Safe transition to boosted load |
| **Forced Induction (Mid Boost)** | 5 to 10 psi | **11.5:1 - 12.0:1** | Charge air cooling and knock prevention |
| **Forced Induction (High Boost)** | > 10 psi | **11.0:1 - 11.5:1** | Maximum combustion safety margin |

---

## 3. Coordinating Fuel Enrichment with Step-Retard

As manifold pressure climbs on a turbocharged or supercharged engine, cylinder pressures and temperatures rise exponentially. To keep the engine safe, the tuner must coordinate fuel enrichment with ignition timing retard:

### Charge Cooling
Dropping the target AFR from 12.5 down to 11.0 as boost climbs dumps excess fuel into the cylinder. This unburnt liquid fuel vaporizes in the chamber, absorbing heat and lowering intake charge temperatures, which suppresses detonation.

### Combusting Velocity
Richer mixtures burn slower. To prevent the peak pressure from occurring too late, or to prevent pre-ignition, the ignition timing must be retarded in a progressive curve (a "step-retard") matching the fuel enrichment curve. For example, retarding timing by 0.5° per psi of boost under 5 psi, and increasing to 1.0° per psi of boost above 10 psi, ensures the spark is fired at the optimal crank angle for safety.

Refer to the [tuning timing guide](/cars/ignition/tuning-timing) for details on calculating total ignition advance.

## Related Articles
- [Introduction to ECU Tuning](/cars/fueling/ecu-tuning)
- [How to Calibrate Spark Timing](/cars/ignition/tuning-timing)
- [Integrating a Wideband O2 Controller](/cars/fueling/wide-band-o2)
