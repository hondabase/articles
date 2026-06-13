---
summary: 'P0A 9495 OBD1 Accord EX attached pic is a 94 P0AA51 PCB is IPT 02D010B01502 The data below has been copied over from the P13 page as a place holder.'
applies_to:
  obd: [1]
  brand: Honda
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

# P0A

P0A 94-95 [OBD1](/cars/electronics/obd1) Accord EX attached pic is a 94 P0A-A51 
[PCB](/cars/electronics/pcb) is IPT 02D010B0-1502 The data below has been copied over from the P13 page as a place holder. Only a few of the locations are actually known at this time.

###  [RAM](/cars/electronics/ram) 

| **Location** | **Bytes** | **Description** | **Notes** | | :--- | :--- | :--- | :--- | | | 1 | MAP sensor | | | | 1 | TPS Sensor | [OBD1\\_8bit TPS](/cars/electronics/obd1-8bit-tps) | | | 2 | [RPM](/cars/electronics/rpm) in 16bit form | | | | 1 | [ECT](/cars/electronics/ect) Sensor | ?? | | | 1 | [VSS](/cars/electronics/vss) Sensor | km/h | | | 1 | Column of table | See [ROM](/cars/electronics/rom) @6050 - mBar scale | | | 1 | Row of low cam table | See [ROM](/cars/electronics/rom) @6000 - low cam [RPM](/cars/electronics/rpm) scale | | | 1 | Row of high cam table | See [ROM](/cars/electronics/rom) @6028 - high cam [RPM](/cars/electronics/rpm) scale | | | 2 | [CEL](/cars/electronics/cel) Word #1 | contains 0x0000 otherwise a bit depending on [CEL](/cars/electronics/cel) | | | 2 | [CEL](/cars/electronics/cel) Word #2 | contains 0x0000 otherwise a bit depending on [CEL](/cars/electronics/cel) | | | 2 | [CEL](/cars/electronics/cel) Word #3 | contains 0x0000 otherwise a bit depending on [CEL](/cars/electronics/cel) | | | 2 | [CEL](/cars/electronics/cel) Word #4 | contains 0x0000 otherwise a bit depending on [CEL](/cars/electronics/cel) | | | 2 | Actual Rev Cut | [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) | | | 2 | Actual Rev Resume | [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) | | | 1 | Current [RPM](/cars/electronics/rpm) in 8bit form | | | | 1b | VTEC Active | ?? | | | 1b | A/C Switch Input | If pin B5 (ACS) is grounded, 0x0224.0 will read 1 | | | 1 | [RPM](/cars/electronics/rpm) in 8bit form | | | | 1 | O2 sensor | ??? | | | 1 | [IAT](/cars/electronics/iat) sensor | 0v-5v 0x00-0xFF | | | 1 | Baro Sensor | 0v-5v 0x00-0xFF | | | 1 | [ECT](/cars/electronics/ect) sensor | 0v-5v 0x00-0xFF | ###  [ROM](/cars/electronics/rom) 

| **Location** | **Bytes** | **Description** | **Notes** | | :--- | :--- | :--- | :--- | | 0C90 | 4 | Checksum Jump Instruction | Change 909DF17F->03A40C00 to disable checksum | | | 2 | High Cam Rev Limit Reset | Moved to memory here as well as the later entries | | | 2 | High Cam Rev Limit Set | Moved to memory here as well as the later entries | | | 1 | Speed Limiter | 0-255km/h (0-159MPH) FF disables speed limiter | | | 1 | VTEC Coolant Temp Check | (0x44 enables, 0xFF disables) | | | 2 | Low Cam Rev Limit Reset | [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) format | | | 2 | Low Cam Rev Limit Set | [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) format | | | 2 | High Cam Rev Limit Reset | [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) format | | | 2 | High Cam Rev Limit Set | [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) format | | 6000 | 40 | Low Cam Rev Scalar 1x40 | Each scalar is in [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) format | | 6028 | 40 | High Cam Rev Scalar 1x40 | Each scalar is in [OBD1\\_16bit RPM](/cars/electronics/obd1-16bit-rpm) format | | 6050 | 10 | Low and High Cam Map Scalar 1x10 | \\[OBD1\\_8bitMBar\\] | | 605A | 40 | A scalar? Or Multiplier? 1x40 | 16bit format | | 6082 | 40 | A scalar? Or Multiplier? 1x40 | 16bit format | | 60AA | 200 | Low Cam Fuel Table | Unknown Conversion Formula | | 6172 | 200 | High Cam Fuel Table | Unknown Conversion Formula | | 623A | 110 | Extra Table - no idea, simular to maps @6316 & 6384 | 10 col x 11 row | | 62A8 | 110 | Extra Table - no idea, simular to maps @6316 & 6384 | 10 col x 11 row | | 6316 | 110 | Extra Table - no idea, all 80s | 10 col x 11 row | | 6384 | 110 | Extra Table - no idea, all 80s | 10 col x 11 row | | 63F8 | 200 | Low Cam Ignition Table | [OBD1\\_8bit Advance](/cars/electronics/obd1-8bit-advance) | | 64C0 | 100 | Extra Low Cam Ignition Table | 10 col x 10 row | | 642E | 100 | Extra Low Cam Ignition Table | 10 col x 10 row | | 659C | 200 | High Cam Ignition Table | [OBD1\\_8bit Advance](/cars/electronics/obd1-8bit-advance) | | 6664 | 100 | Extra High Cam Ignition Table | 10 col x 10 row | | 66D2 | 100 | Extra High Cam Ignition Table | 10 col x 10 row | | 681C | 110 | Extra Table - no idea, all 00s | 10 col x 11 row | | 688A | 120 | Extra Table - no idea, all 00s | 10 col x 12 row | |7FF1|1|Debug/Test mode????| 0xFF enables, 0x00 disables???? [here](/pgmfi/forum/)|4-95 [OBD1](/cars/electronics/obd1) Accord EX attached pic is a 94 P0A-A51 
[PCB](/cars/electronics/pcb) is IPT 02D010B0-1502 | **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [P0A\\_A51.JPG](/pgmfi/wiki/media/library/P0A/P0A_A51.JPG) | mod | 442912 | 18 Feb 2004 - 02:24 | Speedz | |
