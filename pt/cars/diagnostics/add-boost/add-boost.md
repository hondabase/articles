---
summary: 'Learn how to use the Crome ROMEditor "Add Boost" script to expand ECU fuel and ignition tables for forced induction tuning.'
tags: [ecu, tuning, rom, boost, map-sensor]
applies_to:
  obd: [1]
  models: [P06, P28, P30, P72]
complexity: intermediate
---

# Adding Boost Support via Crome ROMEditor

The Crome ROMEditor "Add Boost" script allows for the expansion of standard fuel and ignition tables to accommodate forced induction. By modifying the table structure, the ECU can interpret and map values for manifold absolute pressure (MAP) readings exceeding atmospheric pressure.

## Overview
Crome scripts are compatible with various OBD1 ECU variants, including P06, P28, P30 (EDM, JDM, USDM), and P72. While most scripts are universally compatible, the "Add Boost" script is primarily optimized for the P72 ROM architecture.

> [!IMPORTANT]
> Not all scripts are compatible with every ROM. Always verify the specific ROM compatibility within the Crome interface before applying modifications.

## Technical Implementation
The "Add Boost" script functions by remapping the table dimensions to allocate specific columns for boost pressure.

*   **Table Expansion:** The standard table size is typically expanded from 10x20 to 15x20.
*   **MAP Scaling:** The final five columns are reconfigured to represent positive pressure (boost) rather than atmospheric (NA) values.
*   **ECU Logic:** This modification enables the ECU to reference dedicated fuel and ignition timing values when the MAP sensor detects pressure above atmospheric levels.

## Compatibility
This script is designed to function similarly to the boost tab features found in other tuning platforms like UberData. Ensure your ECU hardware is properly converted for socketing and that you are using a compatible MAP sensor (e.g., 2.5-bar or 3-bar) capable of reading boost pressures.

> [!TIP]
> After applying the "Add Boost" script, verify that your fuel and ignition maps are properly populated in the newly created boost columns to prevent lean conditions or engine knock under load.