---
summary: 'Learn how to utilize ROM editor scripts to expand stock ECU fuel and ignition tables for forced induction applications.'
tags: [ecu, tuning, rom, boost, maps]
applies_to:
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eh]
complexity: intermediate
---

# ECU Boost Table Expansion

ROM editor scripts, such as those used in Crome, allow for the modification of stock ECU fuel and ignition tables to support forced induction. These scripts are compatible with various OBD1 ECU variants, including P06, P28, P30 (EDM, JDM, USDM), and P72.

## Overview
The "Add Boost" script modifies the stock ECU ROM to accommodate positive manifold pressure. By default, stock ECU tables are limited to atmospheric pressure ranges. The script expands these tables to allow the ECU to reference specific fuel and ignition values when the MAP sensor detects pressure exceeding atmospheric levels.

> [!IMPORTANT]
> Not all scripts are compatible with every ROM version. The "Add Boost" functionality is primarily validated for use with P72-based ROMs. Always verify ROM compatibility before applying scripts.

## Technical Implementation
The script performs a structural change to the internal lookup tables within the ROM:

*   **Table Resizing:** The standard table dimensions are typically increased from 10x20 to 15x20.
*   **MAP Scaling:** The additional columns are remapped to correspond to boost pressure values rather than naturally aspirated (NA) vacuum values.
*   **ECU Logic:** This modification enables the ECU to interpret MAP sensor signals above 1.0 bar (atmospheric pressure), allowing for precise fuel and timing adjustments under boost.

## Compatibility
The following ECU models are generally supported for table expansion scripts:

| ECU Model | Region |
| :--- | :--- |
| P06 | USDM |
| P28 | USDM |
| P30 | EDM, JDM, USDM |
| P72 | USDM |

> [!TIP]
> Ensure your MAP sensor is capable of reading the intended boost levels. A stock Honda MAP sensor is typically limited to approximately 10–11 psi. For higher boost levels, an aftermarket 2-bar or 3-bar MAP sensor and corresponding ROM scaling are required.
