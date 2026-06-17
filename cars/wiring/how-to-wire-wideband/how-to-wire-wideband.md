---
summary: 'Installation and configuration guide for AEM wideband O2 sensors on OBD1 Honda ECUs.'
tags: [tuning, wideband, sensors, wiring]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: [dc2, eg, eg-eh]
complexity: advanced
---

# Wideband O2 Sensor Installation Guide

A wideband oxygen sensor (UEGO - Universal Exhaust Gas Oxygen sensor) is essential for precise engine tuning. Unlike a stock narrowband sensor, a wideband provides accurate Air/Fuel Ratio (AFR) measurements across a wide operational range.

---

## Overview

Wideband sensors use a dedicated controller to output a 0–5V analog signal, which corresponds to an AFR range (typically 10:1 to 20:1). This wide range allows for precise fuel map adjustments, whereas narrowband sensors only indicate whether the mixture is richer or leaner than stoichiometry (14.7:1 AFR).

---

## Wiring

The sensor's 0–5V analog output connects directly to the stock ECU narrowband O2 sensor signal pin.

### Wiring Reference

| Connection | Description |
| :--- | :--- |
| **Signal Output** | Connect to the stock ECU O2 signal pin. |
| **Ground** | Use a dedicated, thick-gauge ground for the wideband controller to prevent voltage offsets. |

> **Tip:** Use a T-tap splice or adapter harness to connect to the factory ECU harness without cutting or modifying original chassis wiring.

---

## Software Configuration

To use wideband data in your tuning software (e.g., Honda Tuning Suite or SManager):

1.  **Select ECU Pin:** Configure the tuning software to read the signal from the chosen analog input pin.
2.  **Conversion Table:** Input the voltage-to-AFR scaling values specified in your wideband manufacturer’s manual.
3.  **Calibrate Offset:** If using a physical gauge, compare the software display with the gauge reading and adjust the voltage offset in the software until they match precisely.

*Always ensure your grounding is secure; a poor ground connection is the most common cause of wideband signal instability.*
