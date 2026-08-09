---
title: 'Configuring VTEC & Variable Valve Timing on Standalone ECUs'
summary: 'Parameter setup for Honda VTEC activation: oil pressure switch logic, coolant temp thresholds, hysteresis windows, and TPS load qualifiers.'
tags: [vtec, variable-valve-timing, vss-qualifier, oil-pressure, standalone-tuning]
applies_to:
  models: [civic, integra, accord, prelude]
  chassis: [eg, ek, dc2, bb, cl9]
  engines: [b-series, h-series, k-series, d-series]
complexity: intermediate
sources:
  - title: 'Honda OBD1 VTEC'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2760'
    adapted: true
    author: russian
  - title: 'Direct coil and vtec?'
    url: 'https://rusefi.com/forum/viewtopic.php?t=618'
    adapted: true
    author: Tambralinga
---

# Configuring VTEC & Variable Valve Timing on Standalone ECUs

## Overview

Honda VTEC (Variable Valve Timing and Lift Electronic Control) switches camshaft profiles using a high-pressure oil solenoid. Configuring VTEC on a standalone ECU requires setting proper activation logic, safety qualifiers, and fuel/ignition table switching.

---

## 1. Mandatory VTEC Activation Qualifiers

To prevent engine damage or premature cam engagement, configure the following logical conditions:

1. **RPM Window:** Switch ON at 5000-5500 RPM, Switch OFF at 4800 RPM (200 RPM hysteresis).
2. **Coolant Temperature:** Minimum 60°C (140°F).
3. **Throttle Position (TPS):** Minimum 50% TPS load.
4. **Vehicle Speed (VSS):** Minimum 20 km/h (12 mph).

---

## 2. Solenoid Output Wiring

- **VTEC Solenoid Signal:** Connect to a high-side or low-side relay driver capable of sinking 1.5A to 2.0A at 12V.
- **VTEC Pressure Switch:** Connect 1-pin oil pressure switch to a digital input configured with active-low pull-up.
