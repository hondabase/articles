# ECU Hardware

This page describes how the hardware in an [ECU](/pgmfi/wiki/library/ecu) works, and fun things you can do with it. If you are just wanting to learn how to chip your [ECU](/pgmfi/wiki/library/ecu), you should look at [What You Need](/pgmfi/wiki/library/what-you-need) instead. If you are looking for detailed information about what is going on inside a particular program, you might want to look at [Rom Maps](/pgmfi/wiki/library/rom-maps). Honda definitely did not reinvent the wheel in terms of [ECU](/pgmfi/wiki/library/ecu) technology for each new motor they released. Each "family" of [ECU](/pgmfi/wiki/library/ecu) generally shares one or more [PCB](/pgmfi/wiki/library/pcb)s that are populated with different components in order to run different motors. This really opens the door for [ECUHardware Mods](/pgmfi/wiki/library/ecu-hardware-mods). Additionally, there are design peculiarities that carry over from one family to another. [ECU](/pgmfi/wiki/library/ecu) Families:

- [OBD0](/pgmfi/wiki/library/obd0) [Vacuum Advance](/pgmfi/wiki/library/vacuum-advance) [ECU](/pgmfi/wiki/library/ecu)s from pre-88 cars lacking electronic advance distributors share some common features.
- [OBD0](/pgmfi/wiki/library/obd0) [DPFI](/pgmfi/wiki/library/dpfi) [ECU](/pgmfi/wiki/library/ecu)s from 88-91 cars are useless bastards that are 2 injectors short of being useful
- [OBD0 MPFI](/pgmfi/wiki/library/obd0mpfi) non-vtec [ECU](/pgmfi/wiki/library/ecu)s from 88-91 are a definite family.
- [OBD0 Vtec ECUs](/pgmfi/wiki/library/obd0-vtec-ec-us) like the PW0 and PR3 are a definite family.
- [OBD1 Civic Integra ECUs](/pgmfi/wiki/library/obd1-civic-integra-ec-us) are a definite family.
- [OBD1](/pgmfi/wiki/library/obd1) [Prelude Accord](/pgmfi/wiki/library/prelude-accord) [ECU](/pgmfi/wiki/library/ecu)s are a definite family.
- V6ECUs from the Acura/Rover/Honda Legend V6 cars, NSX and (?) V6 Accord have many common features.
- [OBD2 A](/pgmfi/wiki/library/obd2a) [ECU](/pgmfi/wiki/library/ecu)s are quite similar.
- [OBD2 B](/pgmfi/wiki/library/obd2b) [ECU](/pgmfi/wiki/library/ecu)s are quite similar.
- [OBD2 K](/pgmfi/wiki/library/obd2k) [ECU](/pgmfi/wiki/library/ecu)s are an evolution of [OBD](/pgmfi/wiki/library/obd)2B [ECU](/pgmfi/wiki/library/ecu)s designed to run K-series motors

If you want to learn about how the Oki 66K [MCU](/pgmfi/wiki/library/mcu) works, you should look at [66k Assembler Docs](/pgmfi/wiki/library/66k-assembler-docs). There are many [ECUHardware Mods](/pgmfi/wiki/library/ecu-hardware-mods) you can do to change how [ECU](/pgmfi/wiki/library/ecu) hardware works. Honda often used [MCU](/pgmfi/wiki/library/mcu)s that had internal (on-chip) programs. These were often copy protected. There are [Mcu Readers](/pgmfi/wiki/library/mcu-readers) to defeat the copy protection. Ever wonder who designed honda's [ECU](/pgmfi/wiki/library/ecu)s? [Kehein Indiana Precision Technology](/pgmfi/wiki/library/kehein-indiana-precision-technology) is to blame... It is possible to switch between more than one program on your oversized [EEPROM](/pgmfi/wiki/library/eeprom). All you need to do is add a pullup resistor to the extra address lines (A15, A16, Etc.), then to switch them, just add a debounced switch to the address lines to ground them. **Here is a diagram of 28 &amp; 32 pin EEPROMS:**- [EEPROM](/pgmfi/wiki/library/eeprom) pinouts: 
     ![1.32_pin-2-28PinIC.jpg](1.32_pin-2-28PinIC.jpg)

  **Attachment:**  **Modify:**  **Size:**  **Date:**  **Who:**  **Comment:**  ![](/pgmfi/wiki/assets/icn/bmp.gif) [1.32\_pin-2-28PinIC.jpg](1.32_pin-2-28PinIC.jpg)  mod  39713  06 Feb 2007 - 01:39  Jared Karagen  [EEPROM](/pgmfi/wiki/library/eeprom) pinouts
