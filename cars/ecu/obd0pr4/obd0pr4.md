---
summary: 'Technical overview of the hardware variations, barometric sensors, and unique I/O configurations of the OBD0 Acura Integra PR4 ECU.'
tags: [ecu, reference, obd0, pr4]
applies_to:
  make: Acura
  ecus: [PR4]
  models: [integra]
  chassis: [da]
complexity: intermediate
---

# OBD0 Acura Integra PR4 ECU Technical Reference

The OBD0 PR4 ECU is the factory engine control unit for the 1990–1991 Acura Integra, equipped with the 1.8L DOHC B18A1 engine. While the PR4 shares general architecture with other OBD0 multi-point fuel injection (MPFI) ECUs, it features specific hardware configurations and I/O mapping distinct from the Civic/CRX PM6 series.

## 1. Barometric (PA) Sensor Configurations

The PR4 board layout supports two distinct barometric pressure sensor configurations, typically split by production year:

* **Internal PA Sensor:** Select revisions feature the barometric pressure sensor soldered directly to the ECU PCB.
* **External PA Sensor:** Other revisions are configured via board jumpers to interface with an external PA sensor mounted on the vehicle chassis.

> [!IMPORTANT]
> Verify the jumper configuration on the PCB before attempting to swap or replace the PA sensor, as incorrect settings will result in improper fuel trim calculations.

## 2. Pin Repurposing and I/O Mapping

The PR4 utilizes specific pins differently than the standard Civic/CRX PM6 ECU. Refer to the following mapping for diagnostic and wiring purposes:

### Power Steering Idle Compensation
On the Civic PM6, pin **B14** is dedicated to the Electrical Load Detector (ELD). On the Integra PR4, pin **B14** is repurposed to monitor the power steering pressure switch. When the power steering pump creates an engine load at idle, the switch triggers, signaling the ECU to increase idle speed.

### A/C Control Integration
Unlike standard Honda models where the ECU directly triggers the A/C clutch relay, the OBD0 Integra utilizes an external A/C control module located behind the glove box. The PR4 ECU interfaces with this module solely for idle compensation signals.

### Oil Temperature Monitoring
The B18A1 engine block features a factory oil temperature switch. This sensor is routed to the external A/C and radiator fan control module rather than the ECU. This module governs fan operation based on a combination of ambient, coolant, and oil temperatures.

## 3. ECU Component Trace

```wirelist
{
  "title": "PR4 ECU I/O Mapping",
  "variants": [
    {
      "id": "pr4",
      "label": "PR4 (OBD0)",
      "groups": [
        {
          "label": "Input/Output Variations",
          "rows": [
            { "pin": "B14", "signal": "PSPS", "path": "Power Steering Pressure Switch", "note": "Replaces ELD function found on PM6" },
            { "pin": "A11", "signal": "ACIDL", "path": "A/C Control Module", "note": "Idle compensation signal only" }
          ]
        }
      ]
    }
  ]
}
```

::: widget error-codes :::
