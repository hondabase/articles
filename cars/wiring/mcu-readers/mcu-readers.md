---
summary: 'All of the MCU readers described here take advantage of a design flaw of oki MCUs (and the design flaw is present on all MCUs we have seen to date).'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Mcu Readers'
    url: /pgmfi/wiki/library/mcu-readers
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mcu Readers

All of the [MCU](/cars/rom/mcu) readers described here take advantage of a design flaw of oki [MCU](/cars/rom/mcu)s (and the design flaw is present on all [MCU](/cars/rom/mcu)s we have seen to date). [MCU](/cars/rom/mcu)s can use both internal [ROM](/cars/rom/rom) or external [ROM](/cars/rom/rom) for program memory storage, and a GND or +5v signal on [_EA](/cars/rom/ea)(EA prime - normally has line above EA) is used to control whether internal or external program memory is selected. *Oki [MCU](/cars/rom/mcu)s do not [Latch](/cars/rom/latch) the state of the [_EA](/cars/rom/ea) pin on startup - by some clever trickery, the internal code memory can be unmasked after the [MCU](/cars/rom/mcu) has begun executing code. All of the [ROM](/cars/rom/rom) dumpers that take advantage of this flaw operate like this:

- Manually wire an I/O pin to the [_EA](/cars/rom/ea) pin of the [MCU](/cars/rom/mcu). Use a pull up/pull down resistor if necessary.
- Use a [ROM](/cars/rom/rom) that is larger than the internal [ROM](/cars/rom/rom) of [MCU](/cars/rom/mcu). Make sure all address lines are connected as need be.
- Initialize serial port of [MCU](/cars/rom/mcu) for communication with PC
- Jump above the masked [ROM](/cars/rom/rom) area (32k for `66207`, 48k for `66507`, ...)
- Flip state of [_EA](/cars/rom/ea) using I/O pin
- Enter delay loop long enough to allow internal [ROM](/cars/rom/rom) to be masked into memory again
- Copy [ROM](/cars/rom/rom) contents out the serial port

There are several designs that have been tested: - [OBD0 Oki83 C154 Reader](/cars/wiring/obd0-oki83c154-reader) - Blundar's adaptation
- [OBD1 Oki66207 Reader-DIP64](/cars/wiring/obd1-oki66207-reader-dip64) - Doc's original `66207` design for DIP package chips
- [OBD1 Oki66207 Reader-PLCC68](/cars/wiring/obd1-oki66207-reader-plcc68) - John de sol's adapation of Doc's design for [JDM](/cars/sensors/jdm) SMT 66207s
- [OBD2 Oki66507 Reader Nico](/cars/wiring/obd2-oki66507-reader-nico) - Nico's original reader for the `66507`
- OBD2 Oki66507 Reader Didier - Didier's revised design for a `66507` reader

A reader for other chips would require adjusting the board physical package and the code for clock speed and [ROM](/cars/rom/rom) size.
