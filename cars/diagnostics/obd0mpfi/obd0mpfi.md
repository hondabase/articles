---
summary: 'There is a very distinct family of ECUs found in 8891ish OBD0 hondas. The main characteristics of this family: Oki80 C154 or Oki83 C154 MCUs that are essentially Intel8051 with a 12Mhz Clock Speed.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0]
  brand: Acura/Honda
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0MPFI
    url: /pgmfi/wiki/library/obd0mpfi
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0MPFI

There is a very distinct family of [ECU](/cars/ecu/ecu)s found in 88-91ish [OBD0](/cars/rom/obd0) hondas. The main characteristics of this family:

- [Oki80 C154](/cars/diagnostics/oki80c154) or [Oki83 C154](/cars/diagnostics/oki83c154) [MCU](/cars/rom/mcu)s that are essentially [Intel8051](/cars/rom/intel8051) with a 12Mhz [Clock Speed](/cars/sensors/clock-speed).
- Presence of oki 38256 [EPROM](/cars/rom/eprom) on 90-91 models
- [MPFI](/cars/sensors/mpfi) engines w/ 4 injectors
- non-vtec engines
- electronic advance distributors
- Presence of [Oki6260 A](/cars/ecu/oki6260a) [IO](/cars/sensors/io) controller chip
- Presence of NEC [UPD7004 C](/cars/sensors/upd7004c) [ADC](/cars/wiring/adc) chip
- Presence of [5128 XRAM](/cars/rom/5128xram) 2K [SRAM](/cars/sensors/sram) chip

This architecture was also used by Rover in the UK, and appeared to do so for considerably longer than the 4 years this architecture was used in [USDM](/cars/sensors/usdm) and [JDM](/cars/sensors/jdm) cars. A partial list of [OBD0](/cars/rom/obd0) [ECU](/cars/ecu/ecu)s: - PG7 (88-89 Integra D16A1 - **note** the 86-87 version of this [ECU](/cars/ecu/ecu) ran the vacuum advance D16A1 motor. Different family)
- PM6 ([USDM](/cars/sensors/usdm) Civic/CRX Si - D16A6 [SOHC](/cars/sensors/sohc))
- PM7 ([JDM](/cars/sensors/jdm)/EDM Civic/CRX Si - ZC [DOHC](/cars/sensors/dohc))
- PM8 ([USDM](/cars/sensors/usdm) D15B? [SOHC](/cars/sensors/sohc) HF, [EDM](/cars/wiring/edm) D16Z? ZC [DOHC](/cars/sensors/dohc))
- PR4 ([USDM](/cars/sensors/usdm) 90-91 Int
- PR5 ([JDM](/cars/sensors/jdm) Integra ???)
- PP5 (UKDM Rover Cabio?)
- PS9 ([USDM](/cars/sensors/usdm) Civic Ex 4dr D16A6 auto???)
- PK2 ([JDM](/cars/sensors/jdm) Honda Prelude B20A Engine electronic advance)
- PH3 ([JDM](/cars/sensors/jdm) 86-89 Honda Accord B20A)

[Chipping An88-89 ECU](/cars/rom/chipping-an88-89ecu) is not as easy as the 90-91 computers because only the later computers have replaceable external [ROM](/cars/rom/rom)s. Understanding [OBD0 Inter Chip Communication](/cars/ecu/obd0-inter-chip-communication) will be key to figuring out exactly how the [ECU](/cars/ecu/ecu)s work. Attached below is an eagle (4.09) library containing the [MCU](/cars/rom/mcu) (OKI 8xC154), [RAM](/cars/reference/ram) (`M5128`), [ADC](/cars/wiring/adc) (µPD7004) and engine control counter IC ([Oki6260 A](/cars/ecu/oki6260a)) devices for using these components in eagle layout editor.
