---
summary: 'A comprehensive technical guide for socketing and chipping large-case Honda OBD1 ECUs, covering required components and installation procedures.'
tags: [ecu, chipping, socketing, obd1]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# OBD1 Large-Case ECU Chipping Guide

This guide outlines the procedure for modifying large-case OBD1 Honda ECUs to support programmable memory chips (EEPROMs).

## Required Components

To prepare the ECU for tuning, the following components must be installed on the PCB:

*   **28-pin IC Socket:** Allows for the removal and replacement of the memory chip.
*   **29C256 or 27SF512 EEPROM:** The programmable memory chip containing the engine calibration.
*   **74HC373 Latch:** Required for address latching.
*   **1k Ohm Resistor:** For the J1 jumper location.
*   **0.1uF Ceramic Capacitor:** For the C92 location (noise filtering).

> [!IMPORTANT]
> Ensure the PCB is clean and free of flux residue after soldering to prevent signal interference or short circuits.

## Installation Procedure

1.  **Preparation:** Carefully desolder the factory ROM chip if present. Use a solder sucker or desoldering braid to clear the through-holes without damaging the PCB traces.
2.  **Socket Installation:** Install the 28-pin socket. Ensure the notch on the socket aligns with the orientation mark on the PCB silkscreen.
3.  **Logic Components:** Install the 74HC373 latch in the designated position.
4.  **Jumper Configuration:** Install the 1k Ohm resistor at the J1 location to enable the external memory chip.
5.  **Filtering:** Install the 0.1uF capacitor at C92 to stabilize the power supply to the new memory chip.

> [!CAUTION]
> Excessive heat during soldering can lift the copper pads from the PCB. Use a temperature-controlled soldering station set to approximately 350°C (660°F).

## Verification

Once the components are installed, verify the installation by checking for continuity between the socket pins and the corresponding traces on the PCB. Ensure no solder bridges exist between adjacent pins on the 74HC373 latch.

{{> resistor-color-codes }}