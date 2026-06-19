---
summary: 'Explanation of dual-table ROM structures in Honda ECUs, enabling advanced tuning features like VTEC-dependent fuel and ignition maps.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda ECU Dual-Table ROM Structures

Dual-table structures refer to the presence of two distinct sets of fuel and ignition parameters within a single ROM. This architecture allows the ECU to switch between specific calibration maps based on engine operating conditions or external triggers.

## Common Applications

The most prevalent implementation of dual-table logic is for VTEC operation. The ECU utilizes separate tuning maps to accommodate the distinct volumetric efficiency characteristics of the engine profiles:

*   **Low Cam:** Maps optimized for fuel economy and low-end torque.
*   **High Cam:** Maps optimized for peak power and high-RPM airflow.

## Advanced Tuning Implementations

Beyond factory VTEC switching, dual-table structures are utilized for specialized tuning requirements:

*   **Nitrous Control:** Dedicated fuel and ignition tables can be triggered when a nitrous system is active, allowing for real-time compensation of the increased oxygen density and cylinder pressure.
*   **Alternative Fuels:** Dual maps allow for switching between different fuel types (e.g., pump gas vs. E85) if the hardware and software support the transition.

> [!NOTE]
> Dual-table structures are distinct from **Dual ROMs**, which involve hardware-level switching between two separate physical memory chips.

## Related Concepts

*   **[VTEC](/cars/sensors/vtec):** The primary factory trigger for dual-table switching.
*   **[Dual ROMs](/cars/tuning/dual-roms):** Hardware-based solutions for running multiple full ROM images.
*   **[ECU Nitrous Control](/cars/rom/ecu-nitrous-control):** Implementation of secondary tables for power-adder management.
