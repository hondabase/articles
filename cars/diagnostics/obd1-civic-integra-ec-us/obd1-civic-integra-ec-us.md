---
summary: 'Almost all OBD1 ECUs used in 9295 Civics and integras (but NOT preludes, accords, legends, etc.) are more or less electrically compatible.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  brand: Acura/Honda
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Civic Integra EC Us'
    url: /pgmfi/wiki/library/obd1-civic-integra-ec-us
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 Civic Integra EC Us

Almost all [OBD1](/cars/wiring/obd1) [ECU](/cars/ecu/ecu)s used in 92-95 Civics and integras (but NOT preludes, accords, legends, etc.) are more or less electrically compatible. With minor tweaks, all sorts of [ECUHardware Mods](/cars/rom/ecu-hardware-mods) are possible. [OBD1 Code Compatibility](/cars/wiring/obd1-code-compatibility) describes how to mix and match code and [ECU](/cars/ecu/ecu)s. This generation of [ECU](/cars/ecu/ecu) uses a [66207](/cars/sensors/66207) [MCU](/cars/rom/mcu). Most [ECU](/cars/ecu/ecu)s ship with the program to run them in internal [ROM](/cars/rom/rom). The provision for an external [ROM](/cars/rom/rom) was made in the board design, and it can be activated by adding a [74 HC373](/cars/rom/74hc373), a resistor, two capacitors, [J1](/cars/rom/obd1j1) and a socket for the [ROM](/cars/rom/rom) itself. <- This mostly refers to the [USDM](/cars/sensors/usdm) [ECU](/cars/ecu/ecu)'s. I have not seen evidence otherwise for [JDM](/cars/sensors/jdm) as most already have external [ROM](/cars/rom/rom)'s present. Not sure for [EDM](/cars/wiring/edm) . The [82 C55](/cars/ecu/82c55) chip present on the [ECU](/cars/ecu/ecu) board is an [IO](/cars/sensors/io) controller that is used to drive most outputs. [J12 ](/cars/wiring/obd1j12) controls how the [ECU](/cars/ecu/ecu)'s serial interface works. Important for [Data Logging](/cars/diagnostics/data-logging). dj_spark - 21 Feb 2006 : [EDM](/cars/wiring/edm) P28/P30 [ECU](/cars/ecu/ecu)s are modded in the same way by adding the same components like the [USDM](/cars/sensors/usdm) version.
