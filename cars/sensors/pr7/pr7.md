---
summary: 'Technical hardware overview and specifications for the PR7 OBD1 ECU used in 1991–1994 Acura NSX models.'
tags: [ecu, nsx, obd1, hardware, reference]
applies_to:
  brand: Acura
  models: [nsx]
  chassis: [na1]
complexity: beginner
---

# PR7 OBD1 ECU Technical Reference

The PR7 ECU is the factory engine control unit utilized in 1991–1994 Acura NSX (NA1) vehicles. It operates on the OBD1 communication standard and manages the C30A engine platform.

## Hardware Overview

The PR7 utilizes a unique architecture compared to standard B-series or D-series OBD1 ECUs. 

> [!IMPORTANT]
> While the PR7 shares the OBD1 connector physical interface, the internal pinout and logic are specific to the NSX C30A engine. Do not attempt to swap this ECU into other Honda/Acura chassis without verifying pin-for-pin compatibility.

## Technical Specifications

| Feature | Specification |
| :--- | :--- |
| **Generation** | OBD1 |
| **Vehicle Application** | 1991–1994 Acura NSX |
| **Engine** | C30A |
| **Transmission** | Manual / Automatic (Variant dependent) |

## Component Identification

The PR7 board layout is optimized for the dual-bank ignition system required by the NSX V6 engine.

```carousel
![Top view of PR7 PCB](pr7_top.jpg)
*Top view of the PR7 PCB showing the main processor and capacitor banks*
<!-- slide -->
![Bottom view of PR7 PCB](pr7_bottom.jpg)
*Bottom view of the PR7 PCB showing the solder side and trace routing*
```

## Diagnostics

Use the following tool to reference error codes associated with the PR7 ECU and the C30A engine management system.

::: widget error-codes :::

## Wiring Reference

For specific sensor integration, refer to the standard OBD1 wiring conventions.

{{> obd1-pinout-reference }}

> [!TIP]
> When performing diagnostics on the PR7, ensure the main relay is functioning correctly, as NSX-specific electrical loads can cause intermittent voltage drops at the ECU power pins.
