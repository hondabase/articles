---
summary: 'Technical reference for the Honda PT3 OBD1 ECU used in 1990-1993 USDM Accord models with the F22A1 SOHC engine.'
tags: [ecu, obd1, accord, f22a1, hardware]
applies_to:
  obd: [1]
  models: [Accord 1990-1993]
  chassis: [CB7]
complexity: intermediate
---

# Honda PT3 ECU Technical Reference

The PT3 ECU is an OBD1 engine control unit utilized in 1990–1993 USDM Honda Accord models equipped with the F22A1 SOHC non-VTEC engine. This unit shares the same circuit board architecture as the EDM PT5 Accord ECU (board ID: 02D01190-1504).

## Board Overview

```carousel
![Front view of PT3 ECU](PT3.jpg)
*Front view of the PT3 ECU PCB*
<!-- slide -->
![Back view of PT3 ECU](PT3-bot.jpg)
*Back view of the PT3 ECU PCB*
```

## Hardware Specifications

The PT3 ECU utilizes standard OBD1 architecture. Key components identified in the USDM PT3-A23 manual variant include:

*   **MCU:** OKI 66911
*   **Logic:** 74HC373
*   **Memory:** 38256

> [!NOTE]
> The PT3 shares its PCB design with the EDM PT5 variant. Ensure you verify the specific board ID (02D01190-1504) when sourcing replacement components or performing modifications.

## ECU Variants and Documentation

| Variant | Application | Details |
| :--- | :--- | :--- |
| **PT3-A54** | 1992 Accord LX (Canada) | Automatic Transmission |
| **PT3-A23** | 1991 Accord EX (USDM) | Manual Transmission |

> [!TIP]
> When performing hardware modifications, always reference the specific board revision printed on the PCB to ensure compatibility with existing pinout and component maps.