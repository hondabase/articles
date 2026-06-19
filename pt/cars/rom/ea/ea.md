---
summary: 'EA (EA Prime) is an MCU pin that controls whether the MCU executes from internal ROM or an external ROM chip.'
tags: [ecu, mcu, rom, tuning, obd1]
complexity: beginner
---

# EA Pin (EA Prime) — MCU ROM Control

## Overview

**EA** (EA Prime) is a control pin on the MCU that determines whether the processor executes code from internal ROM or an external ROM chip. On Intel 8051-based MCUs with 40-pin packages, EA is **Pin 31**. In OBD1 ECUs, the **J1** connector controls the EA pin state to enable external ROM installation.

## Pin Specifications

| Parameter | Value |
|-----------|-------|
| **MCU Pin Number** | 31 (40-pin Intel 8051) |
| **Function** | ROM Source Selection |
| **Control Connector** | J1 (OBD1 ECUs) |
| **Logic Level** | High = External ROM; Low = Internal ROM |

## Function

- **EA = High (Logic 1):** MCU executes from external ROM chip
- **EA = Low (Logic 0):** MCU executes from internal ROM

## OBD1 Implementation

In OBD1 ECUs, the J1 connector directly controls the EA pin state. This allows:

- Switching between internal factory ROM and external test/tuning ROM
- Programming and validation of external ROM contents
- Diagnostic and development workflows

> [!IMPORTANT]
> The EA pin state must be properly configured before ECU operation. Incorrect EA configuration can prevent proper code execution or ROM access.

> [!TIP]
> Refer to your specific MCU datasheet and ECU schematic for J1 pinout and EA circuit details.
