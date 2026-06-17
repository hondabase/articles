---
summary: 'Overview of the OBD2 standardized diagnostic protocol (1996+), including its standardized DLC port and diagnostic reporting.'
tags: [diagnostics, obd, emission-control]
applies_to:
  obd: [2]
  brand: Honda/Acura
  models: [accord, civic, del-sol, integra, prelude]
complexity: beginner
---

# OBD2 Diagnostics Standard

The **OBD2 (On-Board Diagnostics II)** protocol was established in the United States in 1996 to standardize the monitoring of vehicle emissions control systems, engine diagnostics, and operational parameters.

---

## Technical Overview
Unlike the proprietary diagnostic systems used in OBD0 and OBD1, OBD2 is a standardized regulatory protocol.

*   **Data Link Connector (DLC):** All OBD2 vehicles must feature a standardized 16-pin connector (SAE J1962).
*   **Diagnostic Trouble Codes (DTCs):** OBD2 utilizes standardized error codes (e.g., `P0420` for catalyst efficiency), making diagnostic tools universal across manufacturers.
*   **Emissions Monitoring:** Systems include secondary sensors (such as a downstream O2 sensor) to actively monitor catalytic converter performance.

## Honda OBD2 Implementation
Honda began transitioning to OBD2 in 1996. While the connector and protocol are standardized, Honda retained some proprietary system communications for non-emissions modules (ABS, SRS, etc.) on specific pin assignments within the 16-pin DLC.

*For specific ECU part numbers and their generation mapping, refer to the [Honda ECU index](/cars/wiring/ecu-connections).*
