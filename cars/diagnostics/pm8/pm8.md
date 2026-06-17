---
summary: 'Technical overview of the Honda PM8 ECU found in 1988–1991 CRX HF models, detailing its unique hardware configuration and relationship to the PM6 and PM7 series.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0]
  models: [crx]
  chassis: [ef]
complexity: beginner
---

# PM8 ECU Technical Reference

The PM8 ECU was utilized in the United States market for the 1988–1991 Honda CRX HF. Unlike many other OBD0 ECUs, the PM8 lacks an external ROM chip, requiring specific hardware considerations for diagnostics and tuning.

## Hardware Overview

The PM8 hardware architecture shares significant similarities with the PM6 and PM7 series, though it features distinct internal configurations. 

> [!NOTE]
> The PM8 does not support standard external ROM replacement methods common to the PM6 or PM7 due to the absence of a socketed external ROM.

### Comparison to Related ECUs

| ECU Model | Architecture | ROM Configuration |
| :--- | :--- | :--- |
| **PM6** | OBD0 | External (Socketed) |
| **PM7** | OBD0 | External (Socketed) |
| **PM8** | OBD0 | Internal (Non-socketed) |
| **PR4** | OBD0 | External (Socketed) |

## Technical Specifications

*   **Application:** 1988–1991 Honda CRX HF (US Market).
*   **Diagnostic Capability:** Compatible with standard OBD0 diagnostic procedures.
*   **Tuning Compatibility:** Limited due to the lack of an external ROM; requires advanced hardware modification for custom mapping.

> [!WARNING]
> Attempting to desolder or modify the internal ROM on a PM8 board carries a high risk of permanent hardware damage. Ensure proper ESD protection and professional-grade desoldering equipment are used if modification is required.