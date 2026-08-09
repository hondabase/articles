---
title: 'Honda K-Series (K20/K24) Cam & Crank Trigger Synchronization & Cam Phasing'
summary: 'Complete guide to Honda K20/K24 Hall effect crank (12+1) and cam trigger decoding, variable timing control (VTC) solenoid PWM tuning, and cam phase tracking.'
tags: [k-series, k20, k24, trigger, vtc, cam-phasing, microrusefi, hellen]
applies_to:
  models: [civic, integra, rsx, accord]
  chassis: [ep3, dc5, cl9]
  engines: [k-series, k20, k24]
complexity: advanced
sources:
  - title: 'MRE Honda K sequential cam trigger configuration'
    url: 'https://rusefi.com/forum/viewtopic.php?t=1972'
    adapted: true
    author: Captainavi
  - title: 'Honda/Acura K-series ECU tuning'
    url: 'https://rusefi.com/forum/viewtopic.php?t=921'
    adapted: true
    author: Hobbs
  - title: 'K24 Swap Project microrusefi'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2431'
    adapted: true
    author: 'K24 Hilux Project'
---

# Honda K-Series (K20/K24) Cam & Crank Trigger Synchronization & Cam Phasing

## Overview

Unlike older distributor-based engines, the Honda K-series family (K20A, K20Z, K24A, K24Z) uses factory digital **Hall effect sensors** operating on a +5V supply. Understanding its 12+1 crank wheel and dual cam trigger wheels is essential for reliable sequential ignition, fuel injection, and dynamic VTC (Variable Timing Control) cam phasing.

---

## 1. Sensor Specifications & Signal Decoding

### Crankshaft Trigger (12+1 Wheel)

- **Sensor Type:** Digital Hall Effect (3-pin: +5V Power, Signal, Sensor Ground).
- **Trigger Wheel:** 12 evenly spaced teeth plus 1 offset pulse wheel mounted behind the crank timing gear.
- **Decoding:** Provides 30-degree mechanical resolution per crank revolution.

### Camshaft Triggers (Intake VTC & Exhaust)

- **Intake Cam Sensor:** 4-tooth uneven pattern. Used for both engine phase sync and real-time VTC intake cam angle position feedback.
- **Exhaust Cam Sensor:** 1-tooth or 4-tooth pattern depending on engine generation (K20A2 vs K20Z3/K24A2).

---

## 2. Standalone ECU Pinout & Wiring

When connecting a standalone ECU (microRusEfi, Hellen 125, Proteus) to a K-series engine harness:

| Sensor | Factory Pin | Wire Color | Standalone Connection |
| --- | --- | --- | --- |
| Crank Position (CKP) | C24 | Blue | Primary Digital Trigger (`Trigger #1`) |
| Intake Cam Position (CMP-I) | C1 | Yellow | Cam Sync & VTC Feedback (`Trigger #2`) |
| Exhaust Cam Position (CMP-E) | C2 | Green/Yellow | Auxiliary Cam Input (`Trigger #3`) |
| Sensor Power | C18 | Yellow/Blue | +5V Reference Supply |
| Sensor Ground | C14 | Green/White | Dedicated Sensor Ground |

---

## 3. Variable Timing Control (VTC) Solenoid Setup

The intake camshaft advances up to 50 degrees continuously via oil pressure metered by the VTC solenoid valve.

> \[!IMPORTANT\] The VTC solenoid requires a high-frequency PWM switching output (typically 250 Hz - 300 Hz) driven by a dedicated low-side driver with flyback diode protection.

### Closed-Loop Cam Phasing Calibration

1. **Zero Angle Calibration:** Set VTC duty cycle to 0% and record raw intake cam angle offset at idle (default fully retarded position = 0 deg).
2. **PID Loop Tuning:** Adjust Proportional, Integral, and Derivative gains so cam angle closely tracks targeted VTC advance table values without oscillation.
3. **Safety Stop Limit:** Enforce maximum advance limits (e.g. 45 deg or 50 deg depending on valve-to-piston clearance on modified engine builds).
