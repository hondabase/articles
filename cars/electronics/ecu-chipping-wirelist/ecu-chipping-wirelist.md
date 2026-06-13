---
summary: 'Pin connections and traces between the MCU, latch, and external EPROM socket on OBD1 Honda ECUs.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - ECU
  - chipping
  - hardware
  - wiring
---

# ECU Chipping Wirelist

This topic is intended to help you debug soldering problems when chipping an [ECU](/cars/electronics/ecu). The first section is generic advice for debuggiing all [ECU](/cars/electronics/ecu)s. The remaining sections contain the wirelists associated with the PROM and 74HC373 latch for known [ECU](/cars/electronics/ecu)s. Please add to the list of [ECU](/cars/electronics/ecu)s with this wirelist, and please add any new wirelists for [ECU](/cars/electronics/ecu)s with different connections. General Debugging Advice: The 373 latch and the ROM socket signals are all connected between those two ICs, plus the 66K MCU, IC9 (a 541 buffer chip) and RM3 (a resistor pack). First, with a continuity tester (I have a DVM that beeps), test each pair of adjacent pins around the 373 latch and the ROM socket to ensure that you have not created a solder bridge between two pins. There should not be continuity between any two adjacent pins. Second, with the continuity tester, check each pin on the 373 latch and then the ROM to ensure it has continuity to at least one of the items that it should be connected to per the data below. Put one probe on the pin where it enters the package, and the other probe on one of the items on the list. I listed the feed-throughs (labeled "FT") in addition to the IC pins, as they can be used to test continuity from the IC pin to the board as well. For the DIPs (Dual Inline Packages), the pins are numbered starting with 1 down the left side with the notch at the top. Sometimes pin one is marked with a dot. The numbers continue back up the right side with the last pin being opposite the first pin at the top. Pin names starting with a "/" are active low. The SIP Single Inline Package) resistor pack RM3 Pin 1 is indicated on the silk screen. The surface mount 66K MCU pin 1 is in the middle of one side of the square package on the JDM P30 board. Some of the pins around the package have pin numbers silk screened on the board so it is easy to find the MCU pins. [ECU](/cars/electronics/ecu) wirelists:

---

JDM P30-901, (If you confirm other [ECU](/cars/electronics/ecu)s that have this wirelist, please list them here) ```

373 Latch:
 
Pin 1 (/OE) -> 373 Pin 10 -> FT -> ROM Pin 14 (GND) -> ROM Pin 20 (/CE) 
Pin 2 (1Q) -> RM3 Pin 5 -> ROM Pin 10 (A0) 
Pin 3 (1D) -> RM3 Pin 9 -> ROM Pin 11 (I/O0) -> 66K Pin 2 (AD0) -> IC9 Pin 11 
Pin 4 (2D) -> RM3 Pin 8 -> ROM Pin 12 (I/O1) -> 66K Pin 3 (AD1) -> IC9 Pin 12 
Pin 5 (2Q) -> ROM Pin 9 (A1) 
Pin 6 (3Q) -> ROM Pin 8 (A2) 
Pin 7 (2D) -> RM3 Pin 7 -> ROM Pin 13 (I/O2) -> 66K Pin 4 (AD2) -> IC9 Pin 13 
Pin 8 (2D) -> RM3 Pin 6 -> ROM Pin 15 (I/O3) -> 66K Pin 5 (AD3) -> IC9 Pin 14 
Pin 9 (4Q) -> ROM Pin 7 
Pin 10 (GND) -> 373 Pin 1 -> FT -> ROM Pin 14 (GND) -> ROM Pin 20 (/CE) 
Pin 11 (LE) -> C91 -> 66K Pin 24 (ALE) 
Pin 12 (5Q) -> ROM Pin 4 (A6) 
Pin 13 (5D) -> ROM Pin 18 (I/O6) -> 66K Pin 8 (AD6) -> IC9 Pin 17 
Pin 14 (6D) -> ROM Pin 19 (I/O7) -> 66K Pin 9 (AD7) -> IC9 Pin 18 
Pin 15 (6Q) -> FT -> ROM Pin 3 (A7) 
Pin 16 (7Q) -> FT -> ROM Pin 5 (A5) 
Pin 17 (7D) -> ROM Pin 17 (I/O5) -> 66K Pin 7 (AD5) -> IC9 Pin 16 
Pin 18 (8D) -> ROM Pin 16 (I/O4) -> 66K Pin 6 (AD4) -> IC9 Pin 15 
Pin 19 (8Q) -> ROM Pin 6 (A4) 
Pin 20 (VCC) -> C49 -> ROM Pin 28 (VCC) -> ROM Pin 1 (/WE) 

ROM Socket:
 
Pin 1 (VCC) -> ROM Pin 28 (VCC) -> C49 -> 373 Pin 20 (VCC) 
Pin 2 (A12) -> 66K Pin 14 (A12) 
Pin 3 (A7) -> FT -> 373 Pin 15 (6Q) 
Pin 4 (A6) -> FT -> 373 Pin 12 (5Q) 
Pin 5 (A5) -> FT -> 373 Pin 16 (7Q) 
Pin 6 (A4) -> 373 Pin 19 (8Q) 
Pin 7 (A3) -> 373 Pin 9 (4Q) 
Pin 8 (A2) -> FT -> 373 Pin 6 (3Q) 
Pin 9 (A1) -> FT -> 373 Pin 5 (2Q) 
Pin 10 (A0) -> RM3 Pin 5 -> FT -> 373 Pin 2 (1Q) 
Pin 11 (I/O0) -> RM3 Pin 9 -> 373 Pin 3 (1D) -> 66K Pin 2 (AD0) -> IC9 Pin 11 
Pin 12 (I/O1) -> RM3 Pin 8 -> 373 Pin 4 (2D) -> 66K Pin 3 (AD1) -> IC9 Pin 12 
Pin 13 (I/O2) -> RM3 Pin 7 -> 373 Pin 7 (3D) -> 66K Pin 4 (AD2) -> IC9 Pin 13 
Pin 14 (GND) -> ROM Pin 20 (/CE) -> FT -> 373 Pin 10 (GND) -> FT -> 373 Pin 1 (/OE) 
Pin 15 (I/O3) -> RM3 Pin 6 -> 373 Pin 8 (4D) -> 66K Pin 5 (AD3) -> IC9 Pin 14 
Pin 16 (I/O4) -> 373 Pin 18 (8D) -> 66K Pin 6 (AD4) -> IC9 Pin 15 
Pin 17 (I/O5) -> 373 Pin 17 (7D) -> 66K Pin 7 (AD5) -> IC9 Pin 16 
Pin 18 (I/O6) -> 373 Pin 13 (5D) -> 66K Pin 8 (AD6) -> IC9 Pin 17 
Pin 19 (I/O7) -> 373 Pin 14 (6D) -> 66K Pin 9 (AD7) -> IC9 Pin 18 
Pin 20 (/CE) -> ROM Pin 14 (GND) -> FT -> 373 Pin 10 (GND) -> FT -> 373 Pin 1 (/OE) 
Pin 21 (A10) -> FT -> 66K Pin 12 (A10) 
Pin 22 (/OE) -> C29 -> R39 (on the back of the board) -> 66K Pin 25 (/PSEN) 
Pin 23 (A11) -> FT -> 66K Pin 13 (A11) 
Pin 24 (A9) -> FT -> 66K Pin 11 (A9) 
Pin 25 (A8 ) -> FT -> 66K Pin 10 (A8 ) 
Pin 26 (A13) -> 66K Pin 15 (A13) 
Pin 27 (A14) -> 66K Pin 16 (A14) 
Pin 28 (VCC) -> ROM Pin 1 (/WE) -> C49 -> 373 Pin 20 (VCC)
-- markolson - 28 Dec 2004 
```

---

USDM P28, P05: (Feed-throughs not noted) ```

373 Latch:
 
Pin 1 (/OE) -> 373 Pin 10 -> ROM Pin 14 (GND)
Pin 2 (1Q) -> ROM Pin 10 (A0) 
Pin 3 (1D) -> RM3 Pin 2 -> ROM Pin 11 (I/O0) -> 66K Pin 1 (AD0)
Pin 4 (2D) -> RM3 Pin 3 -> ROM Pin 12 (I/O1) -> 66K Pin 2 (AD1) 
Pin 5 (2Q) -> ROM Pin 9 (A1) 
Pin 6 (3Q) -> ROM Pin 8 (A2) 
Pin 7 (2D) -> RM3 Pin 4 -> ROM Pin 13 (I/O2) -> 66K Pin 3 (AD2) 
Pin 8 (2D) -> RM3 Pin 5 -> ROM Pin 15 (I/O3) -> 66K Pin 4 (AD3) 
Pin 9 (4Q) -> ROM Pin 7 
Pin 10 (GND) -> 373 Pin 1 -> ROM Pin 14 (GND) 
Pin 11 (LE) -> 66K Pin 22 (ALE) 
Pin 12 (5Q) -> ROM Pin 4 (A6) 
Pin 13 (5D) -> RM3 Pin 8 -> ROM Pin 18 (I/O6) -> 66K Pin 7 (AD6) 
Pin 14 (6D) -> RM3 Pin 9 -> ROM Pin 19 (I/O7) -> 66K Pin 8 (AD7) 
Pin 15 (6Q) -> ROM Pin 3 (A7) 
Pin 16 (7Q) -> ROM Pin 5 (A5) 
Pin 17 (7D) -> RM3 Pin 7 -> ROM Pin 17 (I/O5) -> 66K Pin 6 (AD5) 
Pin 18 (8D) -> RM3 Pin 6 -> ROM Pin 16 (I/O4) -> 66K Pin 5 (AD4) 
Pin 19 (8Q) -> ROM Pin 6 (A4) 
Pin 20 (VCC) -> ROM Pin 28 (VCC) -> ROM Pin 1 (/WE) 

ROM Socket:
 
Pin 1 (VCC) -> ROM Pin 28 (VCC) -> 373 Pin 20 (VCC) 
Pin 2 (A12) -> 66K Pin 13 (A12) 
Pin 3 (A7) -> 373 Pin 15 (6Q) 
Pin 4 (A6) -> 373 Pin 12 (5Q) 
Pin 5 (A5) -> 373 Pin 16 (7Q) 
Pin 6 (A4) -> 373 Pin 19 (8Q) 
Pin 7 (A3) -> 373 Pin 9 (4Q) 
Pin 8 (A2) -> 373 Pin 6 (3Q) 
Pin 9 (A1) -> 373 Pin 5 (2Q) 
Pin 10 (A0) -> 373 Pin 2 (1Q) 
Pin 11 (I/O0) -> RM3 Pin 2 -> 373 Pin 3 (1D) -> 66K Pin 1 (AD0) 
Pin 12 (I/O1) -> RM3 Pin 3 -> 373 Pin 4 (2D) -> 66K Pin 2 (AD1) 
Pin 13 (I/O2) -> RM3 Pin 4 -> 373 Pin 7 (3D) -> 66K Pin 3 (AD2) 
Pin 14 (GND) -> 373 Pin 10 (GND) -> 373 Pin 1 (/OE) 
Pin 15 (I/O3) -> RM3 Pin 5 -> 373 Pin 8 (4D) -> 66K Pin 4 (AD3) 
Pin 16 (I/O4) -> RM3 Pin 6 -> 373 Pin 18 (8D) -> 66K Pin 5 (AD4) 
Pin 17 (I/O5) -> RM3 Pin 7 -> 373 Pin 17 (7D) -> 66K Pin 6 (AD5) 
Pin 18 (I/O6) -> RM3 Pin 8 -> 373 Pin 13 (5D) -> 66K Pin 7 (AD6) 
Pin 19 (I/O7) -> RM3 Pin 9 -> 373 Pin 14 (6D) -> 66K Pin 8 (AD7) 
Pin 20 (/CE) -> R54 (and the other side of R54 is connected to GND) 
Pin 21 (A10) -> 66K Pin 11 (A10) 
Pin 22 (/OE) -> R49 -> 66K Pin 23 (/PSEN) 
Pin 23 (A11) -> 66K Pin 12 (A11) 
Pin 24 (A9) -> 66K Pin 10 (A9) 
Pin 25 (A8) -> 66K Pin 9 (A8 ) 
Pin 26 (A13) -> 66K Pin 14 (A13) 
Pin 27 (A14) -> 66K Pin 15 (A14) 
Pin 28 (VCC) -> ROM Pin 1 (/WE) -> 373 Pin 20 (VCC)
-- markolson - 14 Nov 2005 
```

 P05 validated by zcivic and ROM Pin 20 R54 name corrected per his input as well. Thanks. -- markolson - 22 Nov 2005 ---

(Add additional wirelists from [ECU](/cars/electronics/ecu)s with different wirelists here.)
