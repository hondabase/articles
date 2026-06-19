---
summary: 'ROM editors provide a graphical interface for modifying ECU calibration data, allowing users to adjust engine parameters without manual hex editing.'
tags: [tuning, rom, ecu, software]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# ROM Editor Overview

ROM editors are software applications designed to interpret and modify the binary data stored within an ECU's [ROM](/cars/rom/rom). By mapping raw hexadecimal values to human-readable parameters, these tools allow for the precise adjustment of engine management variables.

## Functionality

Instead of manually calculating and overwriting hex addresses, a ROM editor utilizes a definition file (often referred to as a "map pack" or "XDF") to display data in intuitive formats:

*   **2D Graphs:** Used for visualizing curves such as ignition timing or fuel enrichment over RPM.
*   **3D Maps:** Used for complex tables like fuel and ignition maps, where values are plotted against load and RPM.
*   **Scalar Values:** Used for simple constants such as rev limiters, injector sizing, or sensor scaling factors.

> [!NOTE]
> The accuracy of a ROM editor is entirely dependent on the quality and correctness of the definition file used for a specific ECU hardware ID.

## Workflow

The typical process for using a ROM editor involves the following steps:

1.  **Read:** Extract the raw binary image from the ECU using a hardware programmer or diagnostic interface.
2.  **Load:** Open the binary file in the ROM editor and apply the corresponding definition file.
3.  **Edit:** Modify the desired parameters within the graphical interface.
4.  **Checksum:** Recalculate the ROM checksum to ensure the ECU will accept the modified file.
5.  **Write:** Flash the modified binary back to the ECU's memory chip or flash storage.

> [!WARNING]
> Always maintain a backup of the original, unmodified ROM file before performing any edits. Incorrect modifications to critical engine parameters can lead to severe engine damage.
