---
summary: 'Technical specifications and pinout reference for the P0C OBD1 ECU used in 1992-1995 Honda Accord 2.2L models.'
tags: [ecu, accord, obd1, pinout, f22b]
applies_to:
  models: [accord]
  chassis: [cb, cd]
complexity: beginner
---

# P0C OBD1 ECU Reference

The P0C ECU is an OBD1 engine control unit utilized in 1992–1995 Honda Accord models equipped with the 2.2L F22B DOHC non-VTEC engine.

## Technical Specifications

*   **OBD Version:** OBD1
*   **Engine Application:** F22B (DOHC Non-VTEC)
*   **Vehicle Application:** 1992–1995 Honda Accord

> [!NOTE]
> This ECU is specific to the non-VTEC DOHC F22B engine configuration. Ensure compatibility with your specific engine harness before installation.

## ECU Pinout

The following table outlines the primary pinout configuration for the P0C ECU.

```wirelist
{
  "title": "P0C ECU Pinout Reference",
  "variants": [
    {
      "id": "p0c",
      "label": "P0C (OBD1)",
      "groups": [
        {
          "label": "Primary Connectors",
          "rows": [
            { "pin": "A1", "signal": "PG1", "path": "Ground", "note": "Power Ground" },
            { "pin": "A2", "signal": "PG2", "path": "Ground", "note": "Power Ground" },
            { "pin": "A3", "signal": "INJ1", "path": "Injector 1", "note": "Cylinder 1" },
            { "pin": "A4", "signal": "INJ2", "path": "Injector 2", "note": "Cylinder 2" },
            { "pin": "A5", "signal": "INJ3", "path": "Injector 3", "note": "Cylinder 3" },
            { "pin": "A6", "signal": "INJ4", "path": "Injector 4", "note": "Cylinder 4" }
          ]
        }
      ]
    }
  ]
}
```

## Diagnostics

Use the following tool to cross-reference error codes associated with this ECU.

::: widget error-codes :::

## Related Resources

{{> resistor-color-codes }}
