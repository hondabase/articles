---
summary: 'A foundational reference for identifying Honda ECU families, understanding compatibility, and navigating common ECU part numbers.'
tags: [ecu, identification, reference, obd]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, prelude, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, ef, eg, eg-eh, ek]
complexity: beginner
---

# Honda ECU Identification and Compatibility FAQ

Honda ECU codes (e.g., P28, PM6, P72) identify specific ECU families. These codes indicate the hardware architecture and intended application but do not inherently confirm a specific calibration or vehicle compatibility.

## ECU Application Reference

Applications vary significantly by market, production year, transmission type, and emissions calibration. The following table lists common ECU codes and their typical original applications.

| ECU Code | Typical Application |
| :--- | :--- |
| PG6 | 1988-1989 Integra |
| PM5 | 1988-1991 Civic/CRX DX |
| PM6 | 1988-1991 Civic/CRX SOHC Si |
| PM7 | 1989-1991 JDM DOHC ZC EF |
| PM8 | 1988-1991 CRX HF |
| PR2 | 1989-1991 European ZC |
| PR3 | 1989-1991 JDM B16A EF8/EF9 |
| PW0 | 1989-1991 JDM B16A EF8/EF9 and DA6 XSi |
| PR4 | 1990-1991 Integra LS/GS |
| PS9 | 1988-1991 Civic EX Sedan (Automatic) |
| P05 | 1992-1995 OBD1 Civic CX |
| P06 | 1992-1995 OBD1 Civic DX |
| P07 | 1992-1995 OBD1 Civic VX |
| P08 | 1992-1995 OBD1 JDM D15 Civic |
| P0A | 1994-1995 OBD1 Accord EX |
| P13 | 1993-1995 OBD1 Prelude VTEC |
| P14 | 1993-1995 OBD1 Prelude Si (Non-VTEC) |
| P27 | 1992-1995 OBD1 JDM EG Civic 1.6 SOHC |
| P28 | 1992-1995 OBD1 Civic Si/EX |
| P30 | 1992-1995 OBD1 Del Sol DOHC VTEC Si / EG SiR |
| P54-G31 | 1997 Accord 1.8 LS |
| P61 | 1992-1993 OBD1 Integra GS-R |
| P72 | 1994-1995 OBD1 / 1996-2000 OBD2 Integra GS-R |
| P73 | 1996-2000 OBD2 Integra Type R |
| P74/P75 | 1992-1995 OBD1 Integra LS/GS |
| P75 | 1996-2000 OBD2 Integra LS/GS |
| P2N | 1996+ OBD2 Civic HX |
| P2P | 1996+ OBD2 Civic EX |
| P2E | 1996+ OBD2 Civic DX |
| P2M | 1996+ New Zealand Civic SOHC VTEC |
| P2T | 1999+ Civic Si |
| P5P | 1997-2000 OBD2 JDM Prelude Type S |
| PBA | 1997+ Acura 1.6EL |
| PCT | 1998+ JDM Integra/Civic Type R |
| PCX | 1999+ S2000 |

> [!TIP]
> For detailed part-number and market-specific information, refer to the [Honda ECU definition code reference](/cars/ecu/ecu-definition-codes).

## ECU Selection and Compatibility

Selecting the correct ECU requires matching the engine year, engine type, and chassis wiring generation. 

> [!IMPORTANT]
> The correct ECU depends on a combination of factors: market, wiring generation, transmission type, injector impedance, distributor type, and required emissions equipment. Always consult the [OBD generation overview](/cars/wiring/obd) before attempting to swap ECUs between different generations.

## Physical Identification

To identify an ECU, inspect the label on the side of the case. Most units follow a `LLN-LNN` pattern:
*   **Family Code:** The first three characters identify the ECU family.
*   **Suffix:** The suffix often denotes transmission and market variations. Generally, suffixes in the `A00–A49` range indicate manual transmissions, while `A50` and higher often indicate automatic transmissions.

> [!NOTE]
> Suffix ranges are not universal. Always verify the complete part number and internal board revision before assuming compatibility.

## Software and Calibration
Do not assume two ECUs are software-compatible simply because they share the same connector type or family name. Different ECUs may utilize different memory maps, hardware drivers, sensor logic, and output assignments.

Before testing, verify:
*   ECU family and board revision.
*   Checksum validity.
*   Injector configuration.
*   Output pin assignments.

## Contributing to Research
Documentation efforts rely on accurate, verified data. You can contribute by:
*   Providing high-resolution photographs of ECU boards and case labels.
*   Verifying pinouts against factory service manuals.
*   Documenting stock ROM information and checksums.
*   Recording the exact ECU part number, board revision, vehicle, engine, and transmission for all test results.