---
summary: 'An overview of different generations and families of Honda engine control units (OBD0, OBD1, and OBD2) and their compatibility.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ECU
  - reference
---

# Honda ECU Families & Generations

Honda Engine Control Units (ECUs) are grouped into distinct generations and families based on model year, engine configuration, and fuel injection type. Understanding these families is critical when planning engine swaps, OBD conversions, or socketing for custom tuning.

## Overview of ECU Generations
- **Pre-OBD:** Early fuel injection systems (typically 1985–1987).
- **OBD0 DualPoint (DPFI):** Dual-point fuel injection systems (1988–1991, up to 1995 in Europe).
- **OBD0 MultiPoint (MPFI):** Multi-point fuel injection systems for non-VTEC and early VTEC engines (1988–1991).
- **OBD1 MPFI:** The most popular generation for socketing and custom tuning (1992–1995).
- **OBD2 MPFI:** Advanced diagnostics generation (1996+).

## Pre-OBD Families
These early fuel injection designs typically utilize external vacuum advance mechanisms.
- **PG7:** 1986–1987 USDM/JDM Acura Integra (D16A1 engine with vacuum advance).
- **PE7:** 1985–1987 EDM/USDM Civic/CRX Si (EW3/EW4 engines with vacuum advance).
- **PJ1:** 1985–1987 EDM Integra 1.6i-16 / CRX Mk1 1.6i-16.
- **PJ7:** 1986–1987 Prelude 2.0 Si (B20A3 engine).
- **PJ0:** 1986–1989 Accord A20 (vacuum advance).
- **PL2:** 1986–1988 Honda/Acura V6 (`C25`/`C27` engines).

## OBD0 DualPoint (DPFI) Families
Used in entry-level Honda models featuring dual-point injection.
- **PM5:** 1988–1991 Civic Std / CRX DX.
- **PM9:** 1988–1991 Civic Std / CRX DX.
- **P04:** 1992–1995 European EG Civic DXi.
- **PW1:** 1989–1995 European Concerto 1.5i.

## OBD0 MultiPoint (MPFI) Families

### Non-VTEC Civic & Integra (Common Board Design)
The following ECUs share a common circuit board layout with minor component variations:
- **PG7:** 1988–1989 Acura Integra (D16A1 engine with electronic advance).
- **PM6:** 1988–1991 Civic/CRX SOHC Si (D16A6 engine).
- **PM7:** 1989–1991 Civic Si DOHC ZC (JDM EF3 or European Accord A20A).
- **PP5:** 1988–1994 Honda Concerto / UK Rover 216/220/416/420 (GSi/GTi).
- **PR5:** 1990–1991 JDM Integra ZXi (1.6L SOHC).
- **PS9:** 1990–1991 USDM Civic EX (1.6L SOHC, typically automatic).
- **XE5:** 1988–1991 Mugen Race platform (ZC engine).

### Non-VTEC Prelude & Accord B20A
- **PK2:** 1988–1991 Prelude (3rd Gen with B20A engine).
- **PH3:** 1986–1989 JDM Accord (B20A engine).

### Unique OBD0 Board Designs
The PM8 and PR4 feature unique motherboard designs, though their ROM code shares compatibility with other MPFI ECUs:
- **PM8:** 1988–1991 CRX HF.
- **PR4:** 1990–1991 USDM Integra LS/GS (B18A1 engine). Note: An OBD1 version of the PR4 also exists.

## OBD1 (1992–1995) MPFI Families
All 92–95 Civic and Integra ECUs utilize one of three primary motherboard designs. Individual ECUs can be converted or modified (e.g., adding VTEC, automatic transmission control, or secondary intake runners) by populating missing board components.

### 92-95 Civic & Integra OBD1 ECUs
- **P05:** 1992–1995 Civic CX (D15B8 engine, 1-wire O2 sensor).
- **P06:** 1992–1995 Civic DX/LX (D15B7 engine).
- **P07:** 1992–1995 Civic VX (D15Z1 VTEC-E engine, uses a 5-wire or 6-wire lean-burn O2 sensor).
- **P08:** 1992–1995 JDM Civic/CRX VTi/VXi (SOHC VTEC D15B).
- **P27:** 1992–1995 Euro/Asian Civic (non-VTEC 1.6L).
- **P28:** 1992–1995 Civic EX/Si (SOHC VTEC D16Z6).
- **P29:** 1992–1995 JDM Domani (DOHC ZC).
- **P30:** 1992–1995 Del Sol VTEC / JDM Civic SiR (DOHC VTEC B16A).
- **P54:** 1992–1995 JDM Domani/Accord (1.8L B18B DOHC).
- **P61:** 1992–1993 Acura Integra GS-R (DOHC VTEC B17A1).
- **P70:** 1992–1995 JDM Domani (SOHC VTEC ZC - no oil pressure switch).
- **P71:** 1992–1995 JDM Integra (SOHC VTEC D16A).
- **PR3:** 1992–1993 JDM Integra RSi/XSi (DOHC VTEC B16A).
- **PR4:** 1992–1993 Acura Integra RS/LS/GS (B18A1).
- **P72:** 1994–1995 Acura Integra GS-R (DOHC VTEC B18C1 with secondary intake runners/IAB).
- **P74 / P75:** 1992–1995 Acura Integra RS/LS/GS (B18B1).
- **P76:** 1994–1995 JDM Integra (SOHC ZC).
- **P84:** 1992–1995 JDM Civic ETi (VTEC-E, automatic transmission).
- **P91:** 1992–1995 JDM Civic Coupe (SOHC VTEC 1.6L).
- **P1J / P1K:** 1996–2000 UK-manufactured Civic (D14 engines, 75hp/90hp).

### 92-95 Prelude & Accord OBD1 ECUs
These ECUs share similar design principles with the Civic/Integra family but are housed in different casings:
- **P0A:** 1994–1995 Accord EX (F22B1 SOHC VTEC).
- **P0B:** 1992–1995 Accord (F22B2 SOHC non-VTEC).
- **P0C:** 1992–1995 Accord (F22B DOHC non-VTEC).
- **PT3:** 1990–1993 Accord (F22A1/F22A4/F22A6 SOHC).
- **PT5:** 1990–1993 European Accord (F20A7).
- **PT6:** 1991–1993 Accord EX (F22A6, SOHC non-VTEC with IAB).
- **P11:** 1992–1995 Prelude 2.0i (BB3 with F20A4 non-VTEC).
- **P12:** 1992–1995 Prelude S (F22A6 SOHC non-VTEC).
- **P13:** 1993–1995 Prelude VTEC (H22A DOHC VTEC).
- **P14:** 1993–1995 Prelude Si (H23A1 DOHC non-VTEC).
- **P39:** 1992–1995 JDM Prelude BB4 (F22B DOHC non-VTEC).
