---
summary: 'Technical overview of the PR4 ECU, covering both OBD0 and OBD1 hardware variants used in Honda applications.'
tags: [ecu, pr4, obd0, obd1, honda]
applies_to:
  ecus: [PR4]
complexity: beginner
---

# PR4 ECU Technical Overview

The PR4 ECU was produced in two distinct hardware generations to support different OBD standards. Identification of the specific variant is required for tuning, diagnostics, and hardware modification.

## Hardware Variants

The PR4 platform is divided into the following generations:

*   **OBD0 PR4:** Found in early 1990–1991 Integra models.
*   **OBD1 PR4:** Found in 1992–1993 Integra models.

> [!IMPORTANT]
> OBD0 and OBD1 PR4 units are not directly interchangeable due to differences in connector pinouts, internal processor architecture, and communication protocols.

## Technical Specifications

| Feature | OBD0 PR4 | OBD1 PR4 |
| :--- | :--- | :--- |
| **Connector Type** | 3-Plug (OBD0) | 3-Plug (OBD1) |
| **Processor** | Oki M66207 | Oki M66207 |
| **Board Layout** | Large PCB | Compact PCB |

## Related Documentation

For detailed pinouts, component traces, and modification guides, refer to the specific documentation for each generation:

*   [PR4 OBD0 Reference](/cars/ecu/obd0pr4)
*   [PR4 OBD1 Reference](/cars/ecu/obd1pr4)
