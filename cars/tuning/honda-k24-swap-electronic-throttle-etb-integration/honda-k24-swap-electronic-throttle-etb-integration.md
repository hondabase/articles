---
title: 'Honda K24 Swap in Civic / Accord & Electronic Throttle (ETB) Integration'
summary: 'Integrating K24 Drive-By-Wire (DBW) Electronic Throttle Bodies, dual TPS and PPS sensors, PID loop calibration, and CAN-bus cluster integration.'
tags: [k24a, k24a3, etb, dbw, drive-by-wire, pps, tps-pid, can-bus]
applies_to:
  models: [accord, civic, element]
  chassis: [cl9, ep3, yh2]
  engines: [k24, k-series]
complexity: advanced
sources:
  - title: 'Honda K24 ETB TPS issues'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2011'
    author: Jtech2020
    adapted: true
  - title: '2005 Honda Accord K24A3'
    url: 'https://rusefi.com/forum/viewtopic.php?t=1981'
    author: Jtech2020
    adapted: true
  - title: '2004 Honda Civic Si K20'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2436'
    author: AndreyB
    adapted: true
  - title: '2003 Honda Element'
    url: 'https://rusefi.com/forum/viewtopic.php?t=1955'
    author: AndreyB
    adapted: true
---

# Honda K24 Swap in Civic / Accord & Electronic Throttle (ETB) Integration

## Overview

Modern K-series swaps (K24A2, K24A3, K24Z) frequently utilize **Drive-By-Wire (DBW)** Electronic Throttle Bodies (ETB) rather than traditional mechanical throttle cables. This technical guide covers dual TPS/PPS sensor wiring, H-bridge DC motor control, PID tuning, and safety redundancy.

---

## 1. Dual TPS & Pedal Position Sensor Wiring

DBW systems require redundant sensor signals to detect sensor failure or short circuits:

- **TPS 1 & TPS 2:** Opposite voltage slopes mounted on the throttle body shaft.
- **PPS 1 & PPS 2:** Redundant pedal position sensors mounted on the accelerator pedal assembly.

| Sensor Pin | Function | Voltage Range |
| --- | --- | --- |
| TPS 1 | Main Throttle Position | 0.5V (Closed) to 4.5V (WOT) |
| TPS 2 | Secondary Throttle Position | 4.5V (Closed) to 0.5V (WOT) |
| PPS 1 | Main Pedal Position | 0.8V (Released) to 4.2V (Depressed) |
| PPS 2 | Secondary Pedal Position | 0.4V (Released) to 2.1V (Depressed) |

---

## 2. H-Bridge Motor Control & PID Loop Calibration

The ETB DC motor is driven by a high-current H-bridge driver outputting bi-directional PWM power.

> \[!WARNING\] Incorrect PID gain settings can cause aggressive throttle flutter or uncontrolled wide-open throttle behavior. Perform bench calibration with fuel and ignition disabled before initial engine startup.

### Recommended Initial PID Values

- **P (Proportional):** 8.0 - 12.0
- **I (Integral):** 0.15 - 0.30
- **D (Derivative):** 2.0 - 4.0
