---
summary: "blah blah, describe this later. messageboard link. Here's an incomplete part ordering list so far. Parts list MAX233 population option Parts available..."
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
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

# RTP Project

blah blah, describe this later. [messageboard link](/pgmfi/forum/). Here's an incomplete part ordering list so far.

##  Parts list 

###  `MAX233` population option 

- Parts available from Digi-key

|qty|Digi-Key #|Description|Designator(s)|Unit price |1|[399-1760-1-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=399-1760-1-ND)|CAP TANT 220UF 6.3V 20% SMD |`C1` |1.85000 |3|[490-1318-1-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=490-1318-1-ND)|CAP CER .1UF 10V 10% X5R 0402 |`C2`,`C3`,`C6` |0.05100|* |3|[311-10KGCT-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=311-10KGCT-ND)|RES 10K OHM 1/10W 5% 0603 SMD |`R1`-`R3` |0.07000|* |1|[311-100KGCT-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=311-100KGCT-ND)|RES 100K OHM 1/10W 5% 0603 SMD |`R4` |0.07000|* |1|[1N4148WDICT-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=1N4148WDICT-ND)|DIODE SWITCH 75V 400MW SOD-123 |D1 |0.44000 |1|[MMBT4401FSCT-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=MMBT4401FSCT-ND)|TRANSISTOR GP NPN AMP SOT-23 |`Q1` |0.17000 |1|[ED4628-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=ED4628-ND)|28 PIN W/W IC SOCKET GOLD .600 |`IC1` |3.20000|??? |1|[MM74HC00M-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=MM74HC00M-ND)|IC GATE NAND QUAD 2INPUT 14-SOIC |`IC2` |0.39000 |1|[MAX233ACWP-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=MAX233ACWP-ND)|IC 2DVR/2RCVR RS232 5V 20-SOIC |?? |10.7600|eek ||||||>* sold in multiples of 10 - Parts available from allamerican.com

|qty|allamerican #|Description|Designator(s)|Unit price |1|[U634H256SC35](http://www1.allamerican.com/direct/product.asp?T%5FPRDKEY=ZMD+U634H256SC35+++++++++&T%5FMFGCOD=ZMD+&T%5FPRDID=U634H256SC35+++++++++)|256KNVSRAM,POWERSTORE,32KX8 SOP32 (300 MIL)|??|7.50 - Parts available from arrow.com

|qty|arrow #|Description|Designator(s)|Unit price |1|STK14C88-N25|256K [NVSRAM](/cars/electronics/nvsram), 25ns, SOIC32 300mil|??|11.56 `MAX233`'s sure are a ripoff. the extended temp range ones are $14.63! It's probably cheaper just to use a `MAX232` with the damn external caps. [FTDI](http://www.ftdichip.com) [FT232BM](http://www.ftdichip.com/Documents/ds232b12.pdf) USB UART Chips can be ordered from [Saelig](http://www.saelig.com/) $5.75 ea, $4.25q100 - note $30 minimum order. We also need pin headers/receptacles/crimp pins for receptacles, and probably a panel-mount RS232 port for the `MAX233` version and some sort of USB plug for the USB option. And maybe some Kynar wire for the necessary [ECU](/cars/electronics/ecu) modifications.
