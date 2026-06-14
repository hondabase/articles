---
summary: 'There is a very distinct family of ECUs found in 8891ish OBD0 hondas. The main characteristics of this family: Oki80 C154 or Oki83 C154 MCUs that are essentially Intel8051 with a 12Mhz Clock Speed.'
applies_to:
  obd: [0]
  brand: Acura/Honda
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# OBD0MPFI

There is a very distinct family of [ECU](/cars/electronics/ecu)s found in 88-91ish [OBD0](/cars/electronics/obd0) hondas. The main characteristics of this family:

- [Oki80 C154](/cars/electronics/oki80c154) or [Oki83 C154](/cars/electronics/oki83c154) [MCU](/cars/electronics/mcu)s that are essentially [Intel8051](/cars/electronics/intel8051) with a 12Mhz [Clock Speed](/cars/electronics/clock-speed).
- Presence of oki 38256 [EPROM](/cars/electronics/eprom) on 90-91 models
- [MPFI](/cars/electronics/mpfi) engines w/ 4 injectors
- non-vtec engines
- electronic advance distributors
- Presence of [Oki6260 A](/cars/electronics/oki6260a) [IO](/cars/electronics/io) controller chip
- Presence of NEC [UPD7004 C](/cars/electronics/upd7004c) [ADC](/cars/electronics/adc) chip
- Presence of [5128 XRAM](/cars/electronics/5128xram) 2K [SRAM](/cars/electronics/sram) chip

This architecture was also used by Rover in the UK, and appeared to do so for considerably longer than the 4 years this architecture was used in [USDM](/cars/electronics/usdm) and [JDM](/cars/electronics/jdm) cars. A partial list of [OBD0](/cars/electronics/obd0) [ECU](/cars/electronics/ecu)s: - PG7 (88-89 Integra D16A1 - **note** the 86-87 version of this [ECU](/cars/electronics/ecu) ran the vacuum advance D16A1 motor. Different family)
- PM6 ([USDM](/cars/electronics/usdm) Civic/CRX Si - D16A6 [SOHC](/cars/electronics/sohc))
- PM7 ([JDM](/cars/electronics/jdm)/EDM Civic/CRX Si - ZC [DOHC](/cars/electronics/dohc))
- PM8 ([USDM](/cars/electronics/usdm) D15B? [SOHC](/cars/electronics/sohc) HF, [EDM](/cars/electronics/edm) D16Z? ZC [DOHC](/cars/electronics/dohc))
- PR4 ([USDM](/cars/electronics/usdm) 90-91 Int
- PR5 ([JDM](/cars/electronics/jdm) Integra ???)
- PP5 (UKDM Rover Cabio?)
- PS9 ([USDM](/cars/electronics/usdm) Civic Ex 4dr D16A6 auto???)
- PK2 ([JDM](/cars/electronics/jdm) Honda Prelude B20A Engine electronic advance)
- PH3 ([JDM](/cars/electronics/jdm) 86-89 Honda Accord B20A)

[Chipping An88-89 ECU](/cars/electronics/chipping-an88-89ecu) is not as easy as the 90-91 computers because only the later computers have replaceable external [ROM](/cars/electronics/rom)s. Understanding [OBD0 Inter Chip Communication](/cars/electronics/obd0-inter-chip-communication) will be key to figuring out exactly how the [ECU](/cars/electronics/ecu)s work. Attached below is an eagle (4.09) library containing the [MCU](/cars/electronics/mcu) (OKI 8xC154), [RAM](/cars/electronics/ram) (`M5128`), [ADC](/cars/electronics/adc) (µPD7004) and engine control counter IC ([Oki6260 A](/cars/electronics/oki6260a)) devices for using these components in eagle layout editor. | **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/else.gif) [pm6.lbr](pm6.lbr) | mod | 11725 | 05 Dec 2004 - 20:57 | l3st4rd | eagle 4.09 library for some [OBD](/cars/electronics/obd)0 [ECU](/cars/electronics/ecu) components | | *Library.OBD0MPFI moved from Library.OBD0CivicIntegra on 20 Feb 2004 - 00:37 by Home.blundar* - [put it back](https://web.archive.org/web/http://www.pgmfi.org/twiki/bin/rename/Library/OBD0MPFI?newweb=Library&newtopic=OBD0CivicIntegra&confirm=on "Click to move topic back to previous location, with option to change references.") | | :--- |
