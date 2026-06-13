---
summary: 'Almost all OBD1 ECUs used in 9295 Civics and integras (but NOT preludes, accords, legends, etc.) are more or less electrically compatible.'
applies_to:
  obd: [1]
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

# OBD1 Civic Integra EC Us

Almost all [OBD1](/cars/electronics/obd1) [ECU](/cars/electronics/ecu)s used in 92-95 Civics and integras (but NOT preludes, accords, legends, etc.) are more or less electrically compatible. With minor tweaks, all sorts of [ECUHardware Mods](/cars/electronics/ecu-hardware-mods) are possible. [OBD1 Code Compatibility](/cars/electronics/obd1-code-compatibility) describes how to mix and match code and [ECU](/cars/electronics/ecu)s. This generation of [ECU](/cars/electronics/ecu) uses a [66207](/cars/electronics/66207) [MCU](/cars/electronics/mcu). Most [ECU](/cars/electronics/ecu)s ship with the program to run them in internal [ROM](/cars/electronics/rom). The provision for an external [ROM](/cars/electronics/rom) was made in the board design, and it can be activated by adding a [74 HC373](/cars/electronics/74hc373), a resistor, two capacitors, [J1](/cars/electronics/obd1j1) and a socket for the [ROM](/cars/electronics/rom) itself. <- This mostly refers to the [USDM](/cars/electronics/usdm) [ECU](/cars/electronics/ecu)'s. I have not seen evidence otherwise for [JDM](/cars/electronics/jdm) as most already have external [ROM](/cars/electronics/rom)'s present. Not sure for [EDM](/cars/electronics/edm) . The [82 C55](/cars/electronics/82c55) chip present on the [ECU](/cars/electronics/ecu) board is an [IO](/cars/electronics/io) controller that is used to drive most outputs. [J12 ](/cars/electronics/obd1j12) controls how the [ECU](/cars/electronics/ecu)'s serial interface works. Important for [Data Logging](/cars/electronics/data-logging). dj_spark - 21 Feb 2006 : [EDM](/cars/electronics/edm) P28/P30 [ECU](/cars/electronics/ecu)s are modded in the same way by adding the same components like the [USDM](/cars/electronics/usdm) version.
