---
summary: 'All of the MCU readers described here take advantage of a design flaw of oki MCUs (and the design flaw is present on all MCUs we have seen to date).'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# Mcu Readers

All of the [MCU](/cars/electronics/mcu) readers described here take advantage of a design flaw of oki [MCU](/cars/electronics/mcu)s (and the design flaw is present on all [MCU](/cars/electronics/mcu)s we have seen to date). [MCU](/cars/electronics/mcu)s can use both internal [ROM](/cars/electronics/rom) or external [ROM](/cars/electronics/rom) for program memory storage, and a GND or +5v signal on [_EA](/cars/electronics/ea)(EA prime - normally has line above EA) is used to control whether internal or external program memory is selected. *Oki [MCU](/cars/electronics/mcu)s do not [Latch](/cars/electronics/latch) the state of the [_EA](/cars/electronics/ea) pin on startup - by some clever trickery, the internal code memory can be unmasked after the [MCU](/cars/electronics/mcu) has begun executing code. All of the [ROM](/cars/electronics/rom) dumpers that take advantage of this flaw operate like this:

- Manually wire an I/O pin to the [_EA](/cars/electronics/ea) pin of the [MCU](/cars/electronics/mcu). Use a pull up/pull down resistor if necessary.
- Use a [ROM](/cars/electronics/rom) that is larger than the internal [ROM](/cars/electronics/rom) of [MCU](/cars/electronics/mcu). Make sure all address lines are connected as need be.
- Initialize serial port of [MCU](/cars/electronics/mcu) for communication with PC
- Jump above the masked [ROM](/cars/electronics/rom) area (32k for 66207, 48k for 66507, ...)
- Flip state of [_EA](/cars/electronics/ea) using I/O pin
- Enter delay loop long enough to allow internal [ROM](/cars/electronics/rom) to be masked into memory again
- Copy [ROM](/cars/electronics/rom) contents out the serial port

There are several designs that have been tested: - [OBD0 Oki83 C154 Reader](/cars/electronics/obd0-oki83c154-reader) - Blundar's adaptation
- [OBD1 Oki66207 Reader-DIP64](/cars/electronics/obd1-oki66207-reader-dip64) - Doc's original 66207 design for DIP package chips
- [OBD1 Oki66207 Reader-PLCC68](/cars/electronics/obd1-oki66207-reader-plcc68) - John de sol's adapation of Doc's design for [JDM](/cars/electronics/jdm) SMT 66207s
- [OBD2 Oki66507 Reader Nico](/cars/electronics/obd2-oki66507-reader-nico) - Nico's original reader for the 66507
- OBD2 Oki66507 Reader Didier - Didier's revised design for a 66507 reader

A reader for other chips would require adjusting the board physical package and the code for clock speed and [ROM](/cars/electronics/rom) size.
