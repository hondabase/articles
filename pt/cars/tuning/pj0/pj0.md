---
summary: 'The PJ0 ECU for 1986–1989 Accord/Prelude A20A engines exists in multiple regional variants with differing O₂ sensor and EGR control configurations.'
tags: [ecu, reference, tuning, sensors, pj0, accord, prelude, a20a]
applies_to:
  brand: Honda
  models: [Accord, Prelude]
  engine: A20A
  years: [1986, 1987, 1988, 1989]
complexity: intermediate
---

# PJ0 ECU Reference (Accord/Prelude A20A, 1986–1989)

## Overview

The PJ0 ECU for 1986–1989 Accord and Prelude A20A engines was produced across multiple regional markets with significant hardware variations. Certain variants omit O₂ sensor and EGR control functionality, though all models retain vacuum-advance distributor support.

> [!NOTE]
> Most PJ0 ECUs were manufactured by Matsushita. Early models (1986–1987) may use an external 128 KB ROM. California emissions variants are based on the OKI 80C154 microcontroller and always employ external 128 KB ROM storage.

## Manufacturing and ROM Configuration

| **Variant** | **Manufacturer** | **ROM Type** | **Notes** |
|---|---|---|---|
| Standard (non-CA) | Matsushita | Internal or 128 KB external | Typical configuration for most markets |
| California emissions | OKI 80C154 | 128 KB external (always) | Stricter emissions compliance required |
| Early models (86–87) | Matsushita | 128 KB external | Transition period equipment |

## Known Variants

### Canadian 1989 Accord (Matsushita)
- **Part Number:** PJ0-A03
- **Manufacturer:** Matsushita
- **Notes:** Standard domestic variant

### 1989 EDM A20A4 (No EGR, No O₂ Sensor)
- **Part Number:** PJ0-604-2
- **Application:** EX-i trim, 1989 model year
- **Configuration:** EGR and O₂ sensor functionality disabled
- **Variant Type:** EDM (Engine Data Module)

### California Emissions Variant
- **Part Number:** PJ0-L022
- **Microcontroller:** OKI-based architecture
- **ROM:** 128 KB external (required)
- **Certification:** California Air Resources Board (CARB) compliant

### 1986–1987 Prelude SI (USDM)
- **Part Number:** PJ0-666
- **Application:** United States Domestic Market (USDM) Prelude SI
- **Years:** 1986–1987 model range

> [!IMPORTANT]
> Variant availability varies significantly by region and model year. Verify ECU hardware revision against engine block and VIN before modification or replacement.
