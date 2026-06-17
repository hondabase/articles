---
summary: 'Technical overview of the Honda PH3 OBD0 ECU used in 1988-1989 Accord B20A engines, including hardware specifications and diagnostic features.'
tags: [ecu, obd0, tuning, rom, diagnostics, b20a]
applies_to:
  obd: [0]
  models: [Accord]
  chassis: [CA]
complexity: advanced
---

# Honda PH3 ECU Technical Reference

The PH3 OBD0 ECU is utilized in 1988–1989 Honda Accord models equipped with the B20A engine. It features an electronic advance distributor and is architecturally similar to the PK2 ECU found in 1988–1991 Preludes.

## Hardware Specifications

*   **Processor:** OKI 80C154.
*   **ROM:** External 27C256.
*   **Diagnostic Indicators:** Equipped with two onboard diagnostic LEDs.
*   **Compatibility:** The PH3 and PK2 ECUs share nearly identical PCB layouts (approximately 99% similarity).

> [!NOTE]
> The 1986–1987 Accord B20A ECU is based on the OKI 80C514 processor and utilizes a 27C128 ROM. It lacks a dedicated backup processor, instead employing dual OKI processors.

## Configuration and Jumpers

The PH3 ECU includes specific configuration options that vary between manual and automatic transmission variants.

*   **PH3-0732:** Typically associated with automatic transmissions.
*   **PH3-0632:** Typically associated with manual transmissions.

### Jumper BR8
The **BR8** jumper is a critical configuration point on the PH3 board. It is used to disable the secondary O2 sensor (Sensor B) input. When populated, it connects directly to the sensor pin. In the PK2 ECU, this jumper is typically left unpopulated.

## ECU Variants and Documentation

| File | Description |
| :--- | :--- |
| `ph3_0732.jpg` | PH3 Accord B20A 88-89 ECU |
| `ph3_043.jpg` | PH3 Accord B20A 86-87 ECU |
| `ph3-0632_manual.jpg` | PH3-0632 Manual ECU |
| `ph3-0632_manual_options.jpg` | PH3-0632 Manual ECU (Options Close-up) |
| `ph3-0732_auto.jpg` | PH3-0732 Automatic ECU |
| `ph3-0732_auto_options.jpg` | PH3-0732 Automatic ECU (Options Close-up) |
| `BR8-PH3.jpg` | Jumper BR8 detail (O2 Sensor B disable) |

> [!TIP]
> Due to the high degree of hardware commonality between the PH3 and PK2, these units may share compatible firmware programs. Always verify board revisions before flashing.