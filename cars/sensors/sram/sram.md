---
summary: 'Understand how static RAM (SRAM) retains data without a refresh cycle while power remains connected.'
tags: [sram, memory, hardware, reference]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Static RAM (SRAM) Technical Overview

Static Random Access Memory (SRAM) is a type of semiconductor memory that uses bistable latching circuitry to store each bit. Unlike Dynamic RAM (DRAM), which must be periodically refreshed, SRAM retains its data state as long as power is supplied to the circuit.

## Operational Characteristics

SRAM is characterized by its high speed and low power consumption when idle. Because it does not require a refresh cycle, it provides faster access times, making it ideal for cache memory and critical ECU data storage.

> [!NOTE]
> SRAM is volatile memory. All stored data is lost immediately upon the removal of the power supply.

### Key Advantages
* **Speed:** Significantly faster access times compared to DRAM.
* **Efficiency:** No refresh circuitry required, reducing complexity in memory controller design.
* **Stability:** Data remains valid as long as the voltage remains within the specified operating range.

### Technical Comparison
| Feature | SRAM | DRAM |
| :--- | :--- | :--- |
| **Refresh Required** | No | Yes |
| **Speed** | High | Moderate |
| **Complexity** | Low (per cell) | High (requires refresh logic) |
| **Volatility** | Volatile | Volatile |

## Application in ECU Hardware

In automotive engine control units, SRAM is typically utilized for:
* **Real-time data logging:** Storing temporary sensor values during operation.
* **Lookup tables:** Holding active fuel and ignition maps for rapid processor access.
* **Stack/Buffer management:** Handling temporary variables during instruction execution.

> [!IMPORTANT]
> When troubleshooting ECU memory issues, ensure the backup power circuit (often associated with the constant 12V battery feed) is stable. Voltage drops below the SRAM retention threshold will result in the loss of stored trim values and error codes.
