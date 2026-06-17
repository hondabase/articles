---
summary: 'A technical guide on using Nico Analyze for ECU ROM map identification, including configuration of offsets, column settings, and precision scaling.'
tags: [ecu, tuning, rom, diagnostics, software]
applies_to:
  obd: [0, 1, 2]
  models: [civic, crx, del-sol]
  chassis: [ef, eg, eh]
complexity: intermediate
---

# Using Nico Analyze for ECU ROM Map Identification

Nico Analyze is a utility designed to visualize hexadecimal or binary ECU data in a decimal format, facilitating the identification of fuel and ignition maps.

## Configuration Parameters

To effectively identify maps within a ROM file, configure the following parameters in the application:

*   **Offset:** The memory address where the target table begins.
*   **Columns:** Defines the table width. This is critical for proper map alignment.
    *   **OBD0:** Set to 15 columns.
    *   **OBD1:** Set to 10 columns.
*   **Step:** Determines the number of memory locations the program jumps when using the arrow buttons. Setting this to 255 allows for skipping entire tables during a search.
*   **Precision:** Acts as a multiplier for data display.
    *   **Precision 1:** Displays raw decimal values (0–255), corresponding to the 8-bit hex values (00–FF).
    *   **Precision 2:** Displays the 16-bit decimal equivalent of the hex value.

> [!TIP]
> Use the arrow buttons for navigation rather than the scrollbar. Dragging the scrollbar can cause cell misalignment. If cells become misaligned, reset the step to 1 to re-synchronize the data.

## Map Recognition Techniques

Identifying maps requires recognizing logical data distribution patterns. 

*   **Visual Patterns:** Ignition maps typically exhibit a logical distribution of values across the grid. Fuel maps follow similar patterns, though they often incorporate column multipliers at the bottom of the table. Without applying these multipliers, fuel maps may appear to oscillate between lean and rich values across the columns.
*   **Cross-Referencing:** For initial identification, compare the decimal output of the analyzer against known values from established Excel-based map calculators (e.g., PM6 or P30 specific spreadsheets). 
*   **Workflow:** Open a ROM file with known table locations to calibrate your understanding of the offset and column settings before attempting to identify unknown maps in a new ROM.