---
summary: "Technical documentation and architectural reference for the Oki 66K microcontroller series used in Honda ECU hardware."
tags: [ecu, reference, tuning, rom, sensors, diagnostics, oki-66k]
applies_to:
  obd: [0, 1, 2]
  models: [civic, rsx]
  chassis: [all]
complexity: advanced
---

# Oki 66K Architecture Reference

This document provides technical documentation and architectural specifications for the Oki 66K microcontroller series utilized in various Honda ECU platforms.

> [!NOTE]
> The following documentation covers the core instruction set and hardware architecture. Ensure all cross-references are verified against the specific ECU variant hardware manual.

## Architectural Documentation

The Oki 66K series serves as the primary processing unit for early Honda engine management systems. Understanding the register structure and instruction set is essential for custom ROM development and diagnostic analysis.

```carousel
![Page 34-35 of manual: LRB](lrb1.png)
*Page 34-35 of manual: LRB*
<!-- slide -->
![Page 36-37 of manual: LRB](lrb2.png)
*Page 36-37 of manual: LRB*
```

## Technical Specifications

The following table outlines the primary architectural components of the 66K series.

| Feature | Specification |
| :--- | :--- |
| **Architecture** | Oki 66K (16-bit) |
| **Instruction Set** | Proprietary Oki 66K |
| **Addressing Mode** | Segmented |
| **Primary Use** | Engine Control Unit (ECU) |

> [!IMPORTANT]
> When performing assembly-level modifications, verify the checksum requirements for the specific ECU board revision, as these vary significantly between OBD0, OBD1, and OBD2 hardware.