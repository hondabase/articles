---
summary: 'Technical reference for the PW1 ECU, commonly found in D-series Honda applications such as the 1993 Concerto.'
tags: [ecu, pw1, d-series, honda, reference]
applies_to:
  models: [concerto, civic]
  chassis: [ef, eg]
complexity: beginner
---

# PW1 ECU Technical Reference

The PW1 ECU is a factory engine control unit typically found in Honda vehicles equipped with the D15B2 engine, such as the 1993 Honda Concerto.

## Overview
The PW1 is an early-generation Honda ECU utilized for fuel and ignition management on SOHC D-series engines. 

> [!NOTE]
> Ensure your specific engine harness and sensor configuration match the PW1 pinout requirements before installation, as variations exist between regional market specifications.

## Technical Specifications
*   **Engine Compatibility:** D15B2
*   **OBD Standard:** OBD1
*   **Common Applications:** 1993 Honda Concerto

## Diagnostic Resources
Use the following tools to assist with troubleshooting or wiring verification:

::: widget error-codes :::

## Wiring and Pinouts
For detailed signal mapping and component traces, refer to the standard OBD1 ECU wirelist structure.

```wirelist
{
  "title": "PW1 ECU Pinout Reference",
  "variants": [
    {
      "id": "pw1",
      "label": "PW1 (OBD1)",
      "groups": [
        {
          "label": "Primary Sensors",
          "rows": [
            { "pin": "A1", "signal": "IGP1", "path": "Main Relay", "note": "Power Input" },
            { "pin": "A2", "signal": "IGP2", "path": "Main Relay", "note": "Power Input" }
          ]
        }
      ]
    }
  ]
}
```

{{> resistor-color-codes }}
