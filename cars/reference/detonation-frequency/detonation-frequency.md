---
summary: 'Calculate the estimated detonation resonant frequency for Honda engines using the cylinder bore-based resonance formula.'
tags: [tuning, diagnostics, engine-management, detonation]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Detonation Resonant Frequency Calculation

Detonation (knock) produces specific acoustic reverberations within the combustion chamber. These resonant frequencies typically fall within the 2 kHz to 12 kHz range. Understanding these frequencies is essential for configuring knock sensor filtering and digital signal processing in engine management systems.

## Estimation Formula

The resonant frequency of an engine cylinder can be estimated based on the cylinder bore diameter. Use the following formula to calculate the primary detonation frequency:

$$f = \frac{900}{\pi \times r}$$

### Variables
*   **$f$**: Resonant frequency (Hz)
*   **$r$**: Cylinder radius (meters)

> [!IMPORTANT]
> Ensure the cylinder radius is converted to meters before performing the calculation. This formula provides a theoretical baseline; actual resonant peaks may vary based on combustion chamber geometry and piston crown design.

## Frequency Reference Table

| Bore Diameter (mm) | Radius (m) | Estimated Frequency (Hz) |
| :--- | :--- | :--- |
| 75.0 | 0.0375 | ~7,639 |
| 80.0 | 0.0400 | ~7,162 |
| 81.0 | 0.0405 | ~7,073 |
| 84.0 | 0.0420 | ~6,820 |
| 86.0 | 0.0430 | ~6,662 |
| 87.0 | 0.0435 | ~6,586 |

> [!TIP]
> When tuning knock detection windows, use a band-pass filter centered around the calculated frequency to isolate detonation events from mechanical engine noise.