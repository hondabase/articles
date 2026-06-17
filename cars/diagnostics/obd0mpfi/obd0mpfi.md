---
summary: 'Technical overview of the OBD0 MPFI ECU family, featuring Oki 80C154/83C154 architecture and common hardware components found in 1988–1991 Honda vehicles.'
tags: [ecu, obd0, tuning, rom, mcu, diagnostics]
applies_to:
  obd: [0]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
---

# OBD0 MPFI ECU Architecture

The OBD0 MPFI ECU family, utilized in 1988–1991 Honda and Acura vehicles, is defined by a specific hardware architecture centered around the Intel 8051-based microcontroller.

## Hardware Specifications

The primary characteristics of this ECU family include:

*   **MCU:** Oki 80C154 or Oki 83C154 (Intel 8051-based, 12 MHz clock speed).
*   **EPROM:** Oki 38256 (found on 1990–1991 models).
*   **SRAM:** 5128 XRAM (2K).
*   **I/O Controller:** Oki 6260A.
*   **ADC:** NEC UPD7004C.
*   **Engine Management:** MPFI (4-injector), non-VTEC, electronic advance ignition.

> [!NOTE]
> This architecture was also utilized by Rover in the UK for a significantly longer production cycle than the four-year window observed in USDM and JDM markets.

## ECU Identification List

The following ECUs utilize the OBD0 MPFI architecture:

*   **PG7:** 1988–1989 Integra (D16A1). *Note: The 1986–1987 version utilizes a different architecture for the vacuum advance D16A1.*
*   **PM6:** USDM Civic/CRX Si (D16A6 SOHC).
*   **PM7:** JDM/EDM Civic/CRX Si (ZC DOHC).
*   **PM8:** USDM D15B SOHC HF / EDM D16Z ZC DOHC.
*   **PR4:** USDM 1990–1991 Integra.
*   **PR5:** JDM Integra.
*   **PP5:** UKDM Rover Cabrio.
*   **PS9:** USDM Civic EX 4dr (D16A6 Automatic).
*   **PK2:** JDM Prelude (B20A, electronic advance).
*   **PH3:** JDM 1986–1989 Accord (B20A).

## Tuning and Development

> [!IMPORTANT]
> Chipping 1988–1989 ECUs is significantly more complex than 1990–1991 models, as the earlier units lack replaceable external ROM sockets. 

To facilitate custom development, refer to the [OBD0 Inter-Chip Communication](/cars/ecu/obd0-inter-chip-communication) documentation to understand the data exchange between the MCU and peripheral ICs. 

For PCB design and reverse engineering, an Eagle (v4.09) library is available containing the following device footprints:
*   Oki 8xC154 MCU
*   M5128 RAM
*   µPD7004 ADC
*   Oki 6260A Engine Control Counter IC