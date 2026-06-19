---
summary: 'Technical overview of the Automatic Transmission Lockup Solenoid, its function in torque converter management, and its common repurposing in OBD0 Honda ECUs.'
tags: [ecu, transmission, sensors, obd0]
applies_to:
  models: [all]
  chassis: [all]
complexity: beginner
---

# Automatic Transmission Lockup Solenoid

The Automatic Transmission Lockup Solenoid is an electromechanical component integrated into automatic transmissions. It is responsible for engaging the torque converter lockup mechanism under the direct control of the ECU.

> [!NOTE]
> This component is exclusive to automatic transmission vehicles. In manual transmission applications, this output is frequently repurposed for auxiliary control functions.

## Technical Specifications

In the context of OBD0 Honda ECUs, the lockup solenoid is mapped to the following pin:

*   **Pin A8:** Lockup Solenoid Control

## ECU Pinout Reference

The following table details the control signal for the lockup solenoid on supported OBD0 units.

```wirelist
{
  "title": "OBD0 Transmission Control",
  "variants": [
    {
      "id": "obd0",
      "label": "OBD0 ECU",
      "groups": [
        {
          "label": "Transmission Control",
          "rows": [
            { "pin": "A8", "signal": "Lockup Solenoid", "path": "ECU Output -> Solenoid", "note": "Active low control" }
          ]
        }
      ]
    }
  ]
}
```

## Diagnostic Considerations

*   **Functionality:** The ECU monitors engine load, vehicle speed, and throttle position to determine the optimal engagement point for the torque converter lockup.
*   **Repurposing:** Due to the simplicity of the signal, the A8 output is commonly utilized in performance tuning to trigger external devices such as shift lights, nitrous solenoids, or secondary fuel maps, provided the ECU firmware is modified to support the desired logic.
