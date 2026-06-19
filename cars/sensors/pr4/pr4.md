---
summary: 'Technical overview of the PR4 ECU, detailing the differences between the OBD0 and OBD1 variants used in Acura Integra applications.'
tags: [ecu, pr4, obd0, obd1, integra]
applies_to:
  models: [integra]
  chassis: [da, dc2]
complexity: beginner
---

# PR4 ECU Technical Reference

The PR4 ECU was utilized in Acura Integra applications and exists in two distinct generations corresponding to OBD0 and OBD1 standards.

## Variant Overview

The PR4 platform underwent significant hardware revisions to accommodate the transition from OBD0 to OBD1 engine management systems.

| Variant | OBD Generation | Primary Application |
| :--- | :--- | :--- |
| **PR4 (OBD0)** | OBD0 | 1990–1991 Acura Integra (B18A1) |
| **PR4 (OBD1)** | OBD1 | 1992–1993 Acura Integra (B18A1) |

## Technical Specifications

> [!IMPORTANT]
> While the PR4 designation is shared, OBD0 and OBD1 variants are not directly interchangeable due to differences in connector pinouts, internal processor architecture, and sensor signal processing.

### OBD0 PR4
The OBD0 version of the PR4 is characterized by its dual-plug connector layout and reliance on the older Honda OBD0 architecture. It is commonly found in the DA chassis Integra.

### OBD1 PR4
The OBD1 version utilizes the standard three-plug connector layout introduced in 1992. It features updated internal components to support the more advanced OBD1 diagnostic and emissions requirements.

## Related Documentation

For detailed pinout configurations and component-level diagnostics, refer to the specific variant pages:

* [OBD0 PR4 Reference](/cars/ecu/obd0pr4)
* [OBD1 PR4 Reference](/cars/ecu/obd1pr4)

::: widget error-codes :::
