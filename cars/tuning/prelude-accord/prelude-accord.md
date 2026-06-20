---
summary: 'Technical reference for Honda PT6 and PK3 series ECUs, detailing MCU specifications and PROM configurations for OBD-era Prelude and Accord models.'
tags: [ecu, reference, tuning, sensors]
applies_to:
  models: [accord, prelude]
  chassis: [cb, cd, ba]
complexity: beginner
---

# Honda PT6 and PK3 ECU Technical Specifications

This document outlines the hardware configuration for specific Honda PT6 and PK3 series ECUs found in mid-90s Accord and Prelude models.

## Hardware Overview

The following ECU variants utilize the OKI 66911 MCU architecture paired with external 256Kbit PROM storage.

### PT6-A51 (Accord)
*   **MCU:** OKI 66911
*   **Memory:** External 256Kbit PROM

### PK3-A00 (1994 Prelude Si, 1.6L DOHC)
*   **MCU:** OKI 66911
*   **Memory:** External 256Kbit PROM
*   **Logic Components:** 74HC373 latch

> [!NOTE]
> The 74HC373 octal transparent latch is utilized in the PK3-A00 architecture to facilitate address/data bus multiplexing required by the 66911 MCU.

## Technical Reference

| ECU Model | Application | MCU | Memory Type |
| :--- | :--- | :--- | :--- |
| PT6-A51 | Accord | OKI 66911 | 256Kbit PROM |
| PK3-A00 | 1994 Prelude Si | OKI 66911 | 256Kbit PROM |

{{> ecu-safety-precautions }}
