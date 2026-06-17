---
summary: 'Overview of the technical collaboration between Honda and Rover, focusing on shared engine platforms and ECU compatibility.'
tags: [rover, honda, engine-swap, compatibility]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda and Rover Technical Collaboration

Rover utilized various Honda engine platforms and drivetrain components throughout their production history. Understanding these shared architectures is essential for diagnostics, ECU tuning, and engine maintenance.

## Shared Engine Platforms

Rover integrated several Honda-derived powerplants into their vehicle lineup. Key shared platforms include:

*   **ZC Series:** Widely utilized in Rover Cabriolet models. These engines share significant architecture with the Honda D-series, often utilizing compatible OBD-0 and OBD-1 engine management systems.
*   **C-Series (V6):** The Acura Legend V6 platform was adopted for various high-displacement Rover models. These engines typically utilize Honda-specific ECU hardware, requiring specific diagnostic protocols.

## Technical Compatibility

> [!NOTE]
> While Rover vehicles share engine blocks and mechanical components with Honda, wiring harnesses and ECU pinouts may vary significantly due to differences in chassis-side electrical integration.

### ECU Integration
When performing engine swaps or ECU tuning on Rover vehicles equipped with Honda powerplants, verify the following:

1.  **OBD Standard:** Confirm if the vehicle utilizes OBD-0, OBD-1, or OBD-2 protocols.
2.  **Pinout Verification:** Always cross-reference the specific Rover chassis wiring diagram against the corresponding Honda ECU pinout.
3.  **Sensor Compatibility:** Ensure that sensors (MAP, TPS, IACV) match the requirements of the ECU being used, as Rover-specific sensors may occasionally differ in calibration or connector style.

::: widget error-codes :::