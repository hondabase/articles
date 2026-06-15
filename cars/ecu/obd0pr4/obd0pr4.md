---
summary: 'Technical overview of the hardware variations, barometric sensors, and unique I/O configurations of the OBD0 Acura Integra PR4 ECU.'
tags: [ecu, reference]
applies_to:
  brand: Acura
  ecus: [PR4]
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, dc2, ef]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0PR4
    url: /pgmfi/wiki/library/obd0pr4
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Acura Integra PR4 ECU Overview

The OBD0 PR4 ECU is the factory engine control unit for the 1990–1991 Acura Integra (equipped with the 1.8L DOHC B18A1 engine). While the PR4 shares general architecture with other OBD0 multi-point fuel injection (MPFI) ECUs of its era (such as the PM6), it features several unique hardware configurations and sensor handling quirks.

---

## 1. Barometric / Pressure Atmosphere (PA) Sensors

The PR4 board layout supports two distinct barometric sensor configurations, which generally correspond to the split between 1990 and 1991 model years:

*   **Internal PA Sensor:** Some revisions mount the barometric/atmospheric pressure sensor directly onto the ECU circuit board itself.
*   **External PA Sensor:** Other revisions are configured via jumpers to read from an external PA sensor mounted on the vehicle's kick panel or engine bay firewall. 

---

## 2. Pin Repurposing & I/O Quirks

The PR4 routes several standard wiring pins differently compared to the Civic/CRX PM6:

### Power Steering idle Compensation (ELD Pin)
On the Civic PM6, pin **`B14`** is dedicated to the Electrical Load Detector (ELD) sensor. On the Integra PR4, this same input pin is repurposed to monitor the power steering pressure switch. When the power steering pump puts load on the engine at idle (such as during tight parking maneuvers), the switch triggers, telling the ECU to slightly increase idle speed to prevent engine stumbling.

### External A/C Control Integration
On most standard Honda models, the ECU directly triggers the A/C clutch relay. The OBD0 Integra, however, utilizes an externally mounted A/C control module (located behind the glove box). The PR4 ECU interfaces with this module for idle compensation rather than controlling the clutch relay directly.

### Oil Temperature Thermocouple
The B18A1 engine blocks feature a factory oil temperature switch/thermocouple. This sensor is routed to the external A/C and radiator fan control module (which governs fan operation based on ambient, coolant, and oil temperatures) rather than being processed directly by the ECU's fuel or ignition maps.
