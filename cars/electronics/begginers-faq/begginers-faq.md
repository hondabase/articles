---
summary: 'Archived beginner answers for identifying, selecting, and researching Honda ECUs.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - identification
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Begginers FAQ'
    url: /pgmfi/wiki/library/begginers-faq
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Beginner's Honda ECU FAQ

This FAQ preserves introductory ECU identification and compatibility guidance from the
pgmfi wiki. Honda ECU codes such as P28, PM6, and P72 identify ECU families, but do not
by themselves confirm a complete calibration or application.

## What car did this ECU come from?

The archived FAQ lists these common original applications. Applications can vary by
market, year, transmission, and calibration.

| ECU code | Application listed in the archived FAQ |
| :--- | :--- |
| PG6 | 1988-1989 Integra |
| PM5 | 1988-1991 Civic/CRX DX |
| PM6 | 1988-1991 Civic/CRX SOHC Si |
| PM7 | 1989-1991 JDM DOHC ZC EF |
| PM8 | 1988-1991 CRX HF |
| PR2 | 1989-1991 European ZC |
| PR3 | 1989-1991 JDM B16A EF8/EF9; `J00` or `J51` also listed for 1992 |
| PW0 | 1989-1991 JDM B16A EF8/EF9 and DA6 XSi |
| PR4 | 1990-1991 Integra LS/GS |
| PS9 | 1988-1991 Civic EX sedan automatic |
| P05 | 1992-1995 OBD1 Civic CX |
| P06 | 1992-1995 OBD1 Civic DX |
| P07 | 1992-1995 OBD1 Civic VX |
| P08 | 1992-1995 OBD1 JDM D15 Civic |
| P0A | 1994-1995 OBD1 Accord EX |
| P13 | 1993-1995 OBD1 Prelude VTEC |
| P14 | 1993-1995 OBD1 Prelude Si, non-VTEC |
| P27 | 1992-1995 OBD1 JDM EG Civic 1.6 SOHC |
| P28 | 1992-1995 OBD1 Civic Si/EX |
| P30 | 1992-1995 OBD1 Del Sol DOHC VTEC Si / EG SiR |
| P54-G31 | 1997 Accord 1.8 LS |
| P61 | 1992-1993 OBD1 Integra GS-R |
| P72 | 1994-1995 OBD1 and 1996-2000 OBD2 Integra GS-R |
| P73 | 1996-2000 OBD2 Integra Type R |
| P74/P75 | 1992-1995 OBD1 Integra LS/GS |
| P75 | 1996-2000 OBD2 Integra LS/GS |
| P2N | 1996 and later OBD2 Civic HX coupe |
| P2P | 1996 and later OBD2 Civic EX coupe |
| P2E | 1996 and later OBD2 Civic DX coupe |
| P2M | 1996 and later New Zealand Civic SOHC VTEC |
| P2T | 1999 and later Civic Si coupe; OBD generation uncertain in source |
| P5P | 1997-2000 OBD2 JDM Prelude Type S |
| PBA | 1997 and later Acura 1.6EL |
| PCT | 1998 and later JDM Integra/Civic Type R |
| PCX | 1999 and later S2000; OBD generation uncertain in source |

See the larger [Honda ECU definition code reference](/cars/electronics/ecu-definition-codes)
for additional part-number and market information.

## What ECU should be in my car?

The archived FAQ recommends using an ECU that matches the engine year and type. Its
examples include a PM6 for a D16A6, an OBD0 PR4 for an early B18, an OBD1 P72 or P74,
and an OBD2 P73 or P75 where appropriate.

Treat these as broad examples. The correct ECU also depends on market, wiring generation,
transmission, injectors, distributor, sensors, and required emissions equipment. Read the
[OBD generation overview](/cars/electronics/obd) before swapping between generations.

## How do I identify an ECU?

Start with the label on the side of the ECU case. The archived FAQ describes a family
code followed by a suffix, using the simplified pattern `LLN-LNN`, where `L` is a letter
and `N` is a number.

It says the first three characters identify the ECU family. It also describes suffixes
from `A00` through `A49` as generally manual and `A50` or higher as generally automatic.

> [!NOTE]
> Treat the suffix ranges as a clue from the archived FAQ, not a universal rule. Verify the complete part number and board configuration.

## Where can I find the stock program?

The archived FAQ points readers to the ECU definition list for stock binaries. See the
[Honda ECU definition code reference](/cars/electronics/ecu-definition-codes).

## Can I run code from another ECU?

The archived FAQ directs this question to ECU code-compatibility research. Do not assume
two ECUs are software-compatible because they share connectors or similar family names.
Different code bases can use different memory maps, hardware drivers, sensor logic, and
output assignments.

Use a known-compatible base ROM and verify the ECU family, board revision, checksum,
injector configuration, and enabled outputs before testing.

## How can I contribute without writing code?

The original FAQ encouraged non-programmers to test code, photograph and identify ECUs,
help other users, and write documentation. Useful contributions include:

- Photographing ECU boards and case labels
- Verifying pinouts against factory service manuals
- Testing procedures on clearly identified hardware
- Preserving stock ROM information and checksums
- Writing installation and troubleshooting notes

Record the exact ECU part number, board revision, vehicle, engine, transmission, and
results with every contribution.
