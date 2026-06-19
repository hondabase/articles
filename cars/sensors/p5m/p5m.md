---
summary: 'Hardware analysis and component specifications for the P5M 97+ Honda Prelude 2.2VTi (EDM) OBD2 ECU.'
tags: [ecu, reference, sensors, p5m]
applies_to:
  models: [prelude]
  chassis: [bb6]
complexity: intermediate
---

# P5M ECU Hardware Reference (37820-P5M-G61)

This article details the hardware specifications and component layout for the EDM Honda Prelude 2.2VTi (Automatic) ECU, part number 37820-P5M-G61.

## Technical Specifications

*   **Part Number:** 37820-P5M-G61
*   **Board ID:** Denshigiken E2Y-B 0014F-L5000-00
*   **Processor Clock (X1):** 31 MHz

## Component List

| Component | Part Number | Description |
| :--- | :--- | :--- |
| **IC1** | OKI M66509 524 | Microcontroller |
| **IC2** | OKI M6434 32 | Logic/Support IC |
| **IC3** | OKI M6271 | Logic/Support IC |
| **IC5** | MC14051 | Analog-to-Digital Converter |
| **IC22** | NJM2903 (JRC) | Dual Operational Amplifier (DLC Communication) |

## Communication Port (CN2)

The CN2 header is a 5-pin connector used for diagnostic communication.

| Pin | Signal | Description |
| :--- | :--- | :--- |
| 1 | GND | Ground |
| 2 | RX | Receive Data |
| 3 | Vcc | Power Supply |
| 4 | TX | Transmit Data |
| 5 | N/A | Not Connected |

> [!NOTE]
> This ECU is specific to the EDM (European Domestic Market) 1997+ Prelude 2.2VTi Automatic transmission configuration. Ensure hardware compatibility before attempting any modifications or tuning.
