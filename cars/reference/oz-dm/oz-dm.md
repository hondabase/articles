---
summary: 'Technical overview of Australian Domestic Market (OzDM) Honda vehicle specifications and ECU configurations.'
tags: [reference, ozdm, specifications]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Australian Domestic Market (OzDM) Vehicle Specifications

The Australian Domestic Market (OzDM) Honda lineup features unique ECU configurations and hardware specifications distinct from North American (USDM) and Japanese (JDM) counterparts. 

> [!NOTE]
> OzDM vehicles often utilize specific sensor calibrations and emissions hardware tailored to Australian design rules. Always verify the ECU part number against the specific chassis code when performing diagnostics or tuning.

## ECU Hardware Characteristics
OzDM ECUs are generally categorized by their OBD generation. While many share physical architecture with JDM units, they often incorporate specific board-level modifications for local market requirements, such as different fuel maps or ignition timing curves to accommodate local fuel quality.

### Common ECU Variants
| Chassis | Engine | OBD Generation | ECU Identifier |
| :--- | :--- | :--- | :--- |
| EF / DA | B16A / B18A | OBD0 | PG7 / PR3 |
| EG / EH | B16A / D16Y | OBD1 | P30 / P08 |
| EK / EM | B16A / B18C | OBD2 | P2T / P73 |

## Diagnostic Considerations
When working with OzDM vehicles, note the following:

*   **Connector Compatibility:** Ensure the harness pinout matches the specific ECU variant, as some late-model OBD1 OzDM vehicles utilize hybrid pinouts.
*   **Sensor Scaling:** OzDM sensors may require specific scaling factors in tuning software compared to USDM equivalents.
*   **Emissions Equipment:** OzDM models may lack certain secondary air injection or EVAP components found on USDM models, which can affect ECU error code reporting.

> [!IMPORTANT]
> Always cross-reference the ECU serial number with the vehicle's VIN to ensure compatibility before flashing or swapping hardware.