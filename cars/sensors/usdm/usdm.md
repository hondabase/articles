---
summary: 'Technical reference for USDM (United States Domestic Market) OBD1 Honda ECUs, detailing standard features such as ELD, knock control, and hardware characteristics.'
tags: [ecu, obd1, usdm, sensors]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: [eg, dc2]
complexity: intermediate
---

# USDM OBD1 ECU Specifications

United States Domestic Market (USDM) ECUs are characterized by a comprehensive feature set designed to meet North American emissions and diagnostic standards.

## Hardware Characteristics
USDM OBD1 ECUs are housed in a larger, rectangular aluminum casing compared to their JDM counterparts. Internally, these units typically utilize through-hole components rather than surface-mount technology, facilitating easier hardware modification and chip installation.

## Standard Features
USDM OBD1 ECUs include several integrated diagnostic and control systems not consistently found in other regional variants:

*   **Electrical Load Detector (ELD):** Monitors vehicle electrical demand to optimize alternator output.
*   **Knock Sensor:** Standard on DOHC VTEC variants to monitor engine combustion health.
*   **Injector Test Circuit:** Integrated diagnostic circuitry for fuel system monitoring.
*   **Pressure Atmosphere (PA) Sensor:** Used for barometric pressure compensation.

> [!NOTE]
> Unlike many JDM variants, USDM OBD1 ECUs typically do not feature a factory-programmed speed limiter.

## Regional Comparison
| Feature | USDM | JDM | EDM |
| :--- | :--- | :--- | :--- |
| **Case Size** | Large Rectangular | Compact | Varies |
| **Speed Limiter** | No | Yes | Yes |
| **ELD** | Yes | No | Varies |
| **Component Type** | Through-hole | Mixed | Mixed |

{{> ecu-connector-reference }}

> [!TIP]
> For detailed wiring pinouts and sensor signal troubleshooting, refer to the specific ECU model page (e.g., P30, P72, P06).