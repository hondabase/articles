---
summary: 'Technical overview of the PM8 ECU found in 1988-1991 Honda CRX HF models, detailing its hardware architecture and relationship to PM6/PM7 units.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  models: ['CRX HF']
  chassis: [EF]
complexity: beginner
---

# PM8 ECU Technical Reference

The PM8 ECU was factory-equipped in 1988–1991 US-market Honda CRX HF models. 

## Hardware Overview
The PM8 architecture is distinct from other period-correct ECUs due to the absence of external ROM chips. In terms of hardware configuration, the PM8 is closely related to the PM6 and PM7 series ECUs rather than the PR4 series.

> [!NOTE]
> Unlike many other OBD0 Honda ECUs, the PM8 does not utilize a socketed external ROM, which limits traditional chip-based tuning methods.

## Comparison Summary
The PM8 shares significant design commonalities with the following units:

| ECU Model | Architecture Similarity | Notes |
| :--- | :--- | :--- |
| **PM6** | High | Similar hardware layout and component mapping. |
| **PM7** | High | Similar hardware layout and component mapping. |
| **PR4** | Low | Significant differences in board design and logic. |

## Diagnostics and Tuning
Due to the lack of external ROM, modifying the PM8 requires advanced hardware intervention. Users seeking to tune this specific unit should verify board revisions, as they may differ slightly from standard PM6/PM7 configurations.

::: widget error-codes :::
