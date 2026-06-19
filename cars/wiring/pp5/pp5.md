---
summary: 'Technical overview of the PP5 Rover/Honda ECU series, exploring its origins in the Rover-Honda partnership and compatibility.'
tags: [ecu, reference, tuning, rom, hardware]
applies_to:
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
---

# PP5 ECU Reference (Rover/Honda)

The **PP5** series ECUs are historical units resulting from the partnership between Honda and Rover (UK), which led to the installation of Honda engines (specifically the ZC series) into Rover vehicles in the early 1990s.

---

## Technical Overview
These ECUs are similar in design to other Honda OBD0 ECUs of the same era but were adapted for specific Rover vehicle integration.

*   **Variants:** 
    *   **PP5-E01:** Early ROM-less ECU (Rover 216/416/GSi/Gti). Requires external ROM adapters (similar to PM6/PM7). Primarily fitted to vehicles without Lambda sensors.
    *   **PP5-G01 / PP4-G01 / PP4-R00:** Later versions featuring external ROM support, common in UK market vehicles.

## Compatibility
These units are generally **OBD0 non-VTEC ECUs** and are largely swappable with standard OBD0 Honda ECUs (e.g., PM7, PM6), provided wiring and sensor requirements are met.

*   **Atmospheric Pressure Sensor (APS):** Some of these units utilize an APS. If the sensor is missing, the ECU may trigger a Check Engine Light (CEL) or enter limp mode.

*Always verify your ECU’s specific part number and board layout before attempting swaps, as Rover-specific implementation details can vary compared to standard USDM/JDM Honda ECUs.*
