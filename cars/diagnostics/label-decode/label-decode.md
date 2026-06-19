---
summary: 'A comprehensive guide to decoding Honda OBD1 ECU part numbers to identify engine compatibility, market origin, and transmission type.'
tags: [ecu, reference, tuning, diagnostics]
applies_to:
  models: [civic, crx, del-sol, integra]
  chassis: [ef, eg, eh, ek]
complexity: intermediate
---

# Honda OBD1 ECU Label Identification

Honda OBD1 ECU part numbers follow a standardized 37820-ABC-XYZ format. Understanding these identifiers allows for accurate identification of engine application, regional market, and internal hardware revisions.

## Part Number Breakdown

The part number is structured as **37820-ABC-XYZ**.

| Segment | Description |
| :--- | :--- |
| **ABC** | Engine/Chassis application code |
| **X** | Regional market code |
| **Y** | Transmission type (0: Manual, 5: Automatic) |
| **Z** | Board revision (Even: 11F0, Odd: 1720) |

## Regional Market Codes

The middle character (X) of the suffix indicates the intended market for the ECU.

| Code | Market |
| :--- | :--- |
| **A** | USDM (49-state) |
| **L** | USDM (California Emissions) |
| **J** | JDM |
| **G** | EDM |
| **Q** | Australian Market |
| **C** | Canadian Market |
| **N** | Factory Reprogrammed / Service Unit |

> [!NOTE]
> Some JDM units may use numerical prefixes (e.g., 9xx) to denote specific automatic transmission configurations.

## Example Analysis: 37820-P28-A52

Using the breakdown above, the ECU **37820-P28-A52** is identified as follows:

*   **P28**: SOHC VTEC (D16Z6) application.
*   **A**: USDM 49-state market.
*   **5**: Automatic transmission.
*   **2**: 11F0 board revision.

## Hardware Revisions

The final digit (Z) indicates the internal PCB architecture. This is critical when sourcing ECUs for socketing or hardware modifications.

*   **Even Numbers (e.g., 0, 2, 4)**: Typically utilize the **11F0** board architecture.
*   **Odd Numbers (e.g., 1, 3, 5)**: Typically utilize the **1720** board architecture.
