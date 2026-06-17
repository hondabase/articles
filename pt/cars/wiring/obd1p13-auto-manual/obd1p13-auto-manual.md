yaml
---
summary: Convert an OBD1P13 automatic transmission ECU to manual by moving the jumper from RP11 to RP12.
tags:
  - ecu
  - jumper
  - conversion
  - obd1
  - manual
  - automatic
applies_to:
  obd: [1]
  models: [P11, P12, P13, P14, P39]
complexity: beginner
---

# OBD1P13 Automatic to Manual ECU Conversion

## Overview

Most OBD1P13 automatic transmission ECUs feature a jumper bridge at **RP11** with a blank space at **RP12**. By relocating the jumper from RP11 to RP12, you can convert the ECU to manual transmission operation.

## Jumper Relocation Procedure

### Step 1: Locate RP11 and RP12

- **RP11** — Current jumper location (automatic transmission)
- **RP12** — Target jumper location (manual transmission)

### Step 2: Move the Jumper

1. Remove the jumper bridge from **RP11**
2. Install it at **RP12**
3. Power on and verify operation

> [!TIP]
> If your ECU lacks a spare jumper, a standard jumper wire can substitute for the bridge at RP12.

## Transmission Control Resistors

The following resistors control automatic transmission functions and may remain in place:

- **R96**
- **C49**
- **R82**

These resistors relate to automatic transmission control logic but do not prevent manual operation when RP12 is jumpered.

### Dual-Resistor ECUs

Some ECU variants (such as the JDM P13-900) include resistors at both RP11 and RP12 locations. In this case:

1. Remove both resistors entirely
2. Install a jumper wire at **RP12** only

## Applicable Models

This conversion applies to all ECUs sharing the P13 platform PCB:

- P11
- P12
- P13
- P14
- P39

> [!IMPORTANT]
> Verify your ECU model before proceeding. Incorrect jumper placement may result in improper transmission control behavior.