---
summary: 'Step-by-step instructions for converting an OBD0 chassis wiring harness to run an OBD1 ECU.'
applies_to:
  obd: [0, 1]
complexity: advanced
tags:
  - conversion
  - wiring
  - hardware
---

# Kurts OBD0-OBD1

***First attempt to post this OBD1 conversion write-up on wiki.pgmfi.org. Some sections need revision still and they are in italics/bold print. Please send any suggestions to me at [email protected] .***#  D16Z6 installation and OBD0 (88-91) to OBD1 (92-95) wiring conversion - By Kurt_W 

###  Contributions by ~StorminMatt and Noahk (of CRX Resource) 

###  Original April 2001 version reviewed by Lynne R 

###  Slightly improved starting Nov. 2 2003 

This conversion is to an 89 CRX Si though it can also be done to any 4th generation Civic or 2nd generation CRX. It should be also be noted that this conversion can be done using any of the newer D-series Honda engines even though this particular write-up is specifically for a D16Z6 installation. The newer D16Y8 is also a suitable alternative to the D16Z6. I personally have not done a D16Y8 swap, so all particulars are not known to me therefore no information about swapping a Y8 will be included in this write-up (at this time.) Any references to sources for parts are simply for reference. The writers and contributors do not necessarily endorse this institutions. List of the parts used/modified #One slightly used 89 CRX Si #93 D16Z6 (also known as Z6) 1.6L SOHC VTEC #Partial engine harness from the 93 D16Z6 and harness parts (specifically [ECU](/cars/electronics/ecu) plugs) from a 92 Civic DX (automatic) #95 Civic EX P28 [ECU](/cars/electronics/ecu) (manual) #92 Civic Si distributor # #4107 fuel injectors years unknown (more on this later) # 1984-1991 Chilton's Honda Civic/CRX and 1992-1995 Haynes Honda Civic/Del Sol manual or suitable Helms/Honda shop manuals ##  OBD0 to OBD1 conversion 

This was interesting, ordeal yes, ordeal was the correct word. Over all, the process took about 15 hours. Several hours were spent looking over the instructions received from ~StorminMatt for the process making sure they're correct (listed below). The engine harness had to be modified and either the dash harness modified or a converter built to allow the OBD1 [ECU](/cars/electronics/ecu) to be plugged into the 89 dash harness. UPDATE: Since I originally wrote this write-up, the OBD1 conversion has become much more popular therefore pre-built conversion harnesses are available. Most are home built by private individuals, but I don't know of anyone in particular that makes them. Engine Harness Conversion It is necessary to convert the stock harness from the car to which the swap is being done. The OBD1 engine harness will not plug into the OBD0 engine harness due to incompatible plugs. It may be possible to change all the plugs (by removing the gray plugs from the OBD1 harness and replacing the white ones with them on the OBD0 harness) and use the complete OBD1 harness. This was not attempted due to not having the complete OBD1 to work with. Note: Removing the engine harness is recommended to make it easier to modify. Wire colors will be listed in this manner red/grn (indicates red wire with a green stripe). Many wires can be pulled out of plugs by pushing in the front with a small screwdriver for example while giving a gentle tug on the back of the wire. 1. Injection Resistor: There are two ways to deal with the injection resistor and fuel injectors: - Retain the original MPFI fuel injectors and injection resistor. This is the simplest way to go. (Thanks Noahk)
- Convert to the newer injectors. To do this, pull the yel/blk wire from the green plug on the injection resistor. It will be relocated into an open space in a gray 8 wire plug from the OBD1 harness. This OBD1 plug has 8 yel/blk wires leading from it and has a gray cap on it. Removing the cap shows that it has an integrated metal clip that connects all the yel/blk wires together.

2. Injector wiring: - When retaining the original MPFI injectors and injection resistor, nothing needs to be done.
- To use the OBD1 injectors, the injector plugs from the OBD1 harness must be used. `Each` plug has a different color line (brown, red, light blue and plain yellow = 1, 2,3,4 injectors respectively) and a yel/blk wire leading from it. The yel/blk wire from `each` of the injector plugs leads back to the 8 wire plug mentioned in step #1. The OBD0 injector plugs must be cut off and the OBD1 injector plugs soldered on. Match the injector colors to `each` other, as they are the same on both the OBD0 and OBD1 harnesses. Note: On the OBD0 harness, the wire leading from the injector plug to the injector resistor is red/blk. Don't worry about these wires as they only connect the OBD0 injector plug to the injector resistor.

3. Oxygen Sensor (O2): A 4-wire O2 sensor must be added. To do this, 3 lines must be added to the harness. One line runs from the O2 sensor plug to the 8 wire plug mentioned in step #1. This wire is yel/blk. If you did not use the 8 wire plug, i.e. did not convert to OBD1 injectors, you will have to find another power source for the O2 sensor. The second line is a grn/wht line that runs from the O2 sensor plug to any location on the grn/wht wire on the OBD0 harness. The third line is an org/blk line that leads to the [ECU](/cars/electronics/ecu). The final wire is white and serves the same purpose on both the OBD0 and OBD1 cars. This white wire is the O2 sensor wire itself. On the OBD0 engine harness, it's a single wire and has a rather large plug on it. This plug must be cut off and the white wire for the OBD1 plug soldered on. ''This section has been deems unclear by some readers, but useful feedback on how to make it more clear has not been forthcoming....if anyone has any suggestions...'' 4. Distributor Rewiring: There are two plugs to be concerned with, a 7 wire and a 2 wire plug. The lines for the distributor's 7 wire plug can be pulled on both the engine harnesses. Pull the gray OBD1 7 wire plug for the distributor off the OBD1 engine harness and the replace the 7 wire plug on the OBD0 harness with it. Make sure to match the wires coming from the distributor with the matching colors being put into the 7 wire plug. As for the 2 wire plug, the plug has to be cut off the OBD0 harness and OBD1 plug spliced on. 5. VTEC: A wire must be added to the harness for the VTEC activation wire. It's a grn/yel 1 wire plug on the OBD1 harness. This wire must be run into the car and attached to the [ECU](/cars/electronics/ecu). 6. VTEC Oil Pressure Sensor: 2 wire plug, one wire is black and the other blue/blk. The black wire must be run to a ground and the blue/blk wire runs to the [ECU](/cars/electronics/ecu). That's it for the engine harness conversion. ###  Dash/In Car Harness conversion 

This is the fun stuff. There are two ways to do this. Note: Using 92 Civic [ECU](/cars/electronics/ecu) (OBD1) plugs is best for this conversion because it has all the necessary wires for the Z6 [ECU](/cars/electronics/ecu). If 92 [ECU](/cars/electronics/ecu) plugs can't be found try to get the plugs from a Si or EX, otherwise additional wires will need to be added. If these instructions are used for an OBD1 B-series, a knock sensor wire will also need to be added to the plugs (unless [ECU](/cars/electronics/ecu) plugs from an OBD1 Del Sol VTEC are used). 1. Build a conversion harness using the male [ECU](/cars/electronics/ecu) plugs from a 92 Civic or similar and the female plugs from an OBD0 [ECU](/cars/electronics/ecu). To get the plugs off the OBD0 [ECU](/cars/electronics/ecu), unsolder or if necessary cut the [ECU](/cars/electronics/ecu) board with a Dremel tool equipped with a cutoff blade. After the plugs are taken out and cleaned up, the wires from the OBD1 [ECU](/cars/electronics/ecu) plugs can be soldered onto the proper pins from the OBD0 plugs. See below for proper combinations. In addition to matching the wires, 3 wires will have to be routed into the harness to meet up with the OBD1 plugs. These wires are the VTEC wire, the VTEC oil pressure wire and an O2 sensor wire. This is more easily accomplished if done using the a pre-built OBD0 -OBD1 conversion harness as mentioned about in "UPDATE" OR 2. Cut off the OBD0 [ECU](/cars/electronics/ecu) wire plugs and splice the wires from the OBD1 [ECU](/cars/electronics/ecu) plugs to the wires from the OBD0 harness as listed below. You will also have to attach the 3 extra wires mentioned above in method #1. OR 3. Unpin all the wires from the OBD0 connectors. The majority of them are the same size as the "small" OBD1 pins and can simply be inserted into the appropriate spot. The "large" OBD1 pins will need to be crimped or spliced on. (Dave's note) Here is the information on the wiring the OBD1 [ECU](/cars/electronics/ecu). It's originally by ~StorminMatt (thanks Matt) from CRX Resource. Several additions have been made to the listing in the hope of making it more helpful and easy to understand, however, his post has been mostly left intact because he explained it well. "A number of people have asked me how to change the 1988-1991 [ECU](/cars/electronics/ecu) plugs to 1992-1995 plugs in order to use a 1992-1995 [ECU](/cars/electronics/ecu) for any one of a number of applications (SOHC VTEC, 2G B16A, 1992+ B18A/B18B, B17A, B18C, etc.). I figured it would be best to just make one post with this information rather than having to email everybody separately with this information. There are a couple of things to remember here. I personally prefer the numbering system where Honda numbers the pins across rather than the zig-zag system. But I realize a lot of people may prefer or are used to the zig-zag system. So for `each` pin (on `each` plug style), I list two locations for the same pin. The first is given by numbering across. The second (in parenthesis) is by the zig-zag numbering (I hope it is correct). In case I made any errors in conversion AND to make the process of changing the plugs over more goof proof, I also give the color of the wire on the 1992-1995 plug and 1988-1991 plug for the given pins. This should give you a better idea of whether you are connecting the wires together correctly. Also, the first set of pin numbers and wire colors are all on the 1992-1995 plugs and the second set of pin numbers in brackets are the 1988-1991 plugs. ```

A plug (1992-1995 plug)
A1 (A1) ----> A1 (A1)   Injector 1
brn --------> brn
A2 (A3) ----> A2 (A3)   Injector 2
red --------> red
A3 (A5) ----> A3 (A5)   Injector 3
lt. blu ----> lt. blu
A4 (A7) ----> A14 (A12)   Main Relay
grn/yel ----> grn/blk
A5 (A9) ----> A5 (A11)   EACV
grn/wht ----> blu/yel
A7 (A13) ---> B13 (B6)   Check Engine Light
grn/org ----> grn/org
A8 (A15) ---> B2 (B3)   A/C Clutch Relay
blk/red ----> yel
A11 (A21) --> B8 (B15)   Ignition Unit Signal
red/grn ----> wht
A12 (A23) --> A9 (A2)   Main Relay
blk --------> blk
A13 (A25) --> A6 (A13)   Main Relay
yel/blk ----> yel/blk
A14 (A2) ---> A4 (A7)   Injector 4
yel --------> yel
A15 (A4) ---> (VTEC)   grn/yel on the engine harness, your choice elsewhere
org/wht ----> (your choice)
A16 (A6) ---> (O2S heater)   to org/blk on engine harness, your choice elsewhere
org/blk ----> (your choice)
A17 (A8) ---> A15 (A14)   Main Relay
grn/yel ----> grn/blk
A19 (A12) --> B12 (B4)   Radiator Fan Relay
yel/grn ----> yel/grn
A21 (A16) --> B3 (B5)   Alternator
wht/yel ----> wht/yel
A23 (A20) --> A11 (A6)   Purge Control Solenoid
red --------> grn
A24 (A22) --> B9 (B17)   Ignitor Unit
red/grn --------> wht
A25 (A24) --> A10 (A4)   Ground
blk --------> blk
A26 (A26) --> A17 (A18)   "Multiground"
blk/red ----> blk/red

B Plug (1992-1995 plug)
B1 (B1) ----> A7 (A15)   Main Relay
yel/blk ----> yel/blk
B3 (B5) ----> B14 (B8)   A/C Switch
blu/red ----> blu/red
B5 (B9) ----> B7 (B13)   Main Relay
blu/wht ----> blu/wht
B6 (B11) ---> B15 (B10) *
org --------> org
B7 (B13) ---> C2 (C3) *
org/blu ----> org/blu
B8 (B15) ---> C1 (C1) *
blu/grn ----> blu/grn
B9 (B2) ----> A16 (A16)   Multiground
brn/blk ----> brn/blk
B13 (B10) --> B18 (B16)   Vehicle Speed Sensor
yel/blu ----> yel/red
B14 (B12) --> B16 (B12) *
wht --------> wht
B15 (B14) --> C10 (C4) *
wht/blu ----> wht/blu
B16 (B16) --> C9 (C2) *
blu/yel ----> blu/yel

D Plug (1992-1995 Plug - No C plug on 1992-1995 Plugs)
D1 (D1) ----> B1 (B1)   Hazard
wht/blu ----> wht/grn
D2 (D3) ----> (Knock Sensor)   B-series engines only!
red/blu ----> (your choice shielded wire)
D5 (D9) ----> B17 (B14)   Alternator
pnk --------> blu
D6 (D11) ---> C4 (C7)   Throttle Position Sensor
red/blu(or pastel green)  ----> red/blu
D7 (D13) ---> C11 (C6)   Coolant Temperature Sensor
red/wht ----> red/wht
D8 (D15) ---> C3 (C5)   Intake temperature
red/yel ----> red/yel
D9 (D17) ---> C6 (C11)   Map Sensor
wht --------> wht
D10 (D19) --> C8 (C15)   Map Sensor
yel/grn ----> yel/red
D11 (D21) --> C15 (C14)   Map Sensor
grn/blu ----> grn/wht
D12 (D2) ---> C13 (C10)   Brake Switch
grn/wht ----> grn/wht
D13 (D4) ---> B20 (B20)   Service Connector
brn --------> brn
D14 (D6) ---> (VTEC Pressure Switch)   Blue/blk wire in engine harness
org/blu ----> (your choice)
D16 (D10) --> B10 (B19)   Electronic Load Sensor
grn/red ----> grn/red
D18 (D14) --> C16 (C16)   O2 Sensor
wht --------> wht
D21 (D20) --> C7 (C13)   Throttle Position Sensor
yel/wht ----> yel/wht
D22 (D22) --> C14 (C12)   Coolant temp/TPS/O2/etc&#133;ground kind of thing
grn/wht ----> grn/wht
```

The pins marked \* connect to the distributor sensors (crank angle, TDC, and CYP) and while 1988-1991 and 1992-1995 cars both use the same color wires collectively for these sensors (org, org/blu, wht, wht/blu, blu/grn, blu/yel), wires of a given color do NOT necessarily connect to the same sensors in the 1992-1995 cars as in 1988-1991 cars. So if you check the Hasport pin-out, the connections I gave will be incorrect. However, it's actually easier to just match up like colors. If you do this, just remember to match the proper colors on the distributor plug as well. In other words, the org wire on the 1988-1991 engine harness goes into the same spot on the 1992-1995 distributor plug that the org wire went to on the 1992-1995 engine harness. Just don't confuse the fat white wire with the thin white wire on the distributor plug of the 1988-1991 engine harness. The fat white wire on the 1988-1991 harness goes where the fat yel/grn wire on the 1992-1995 harness went (on the 1992-1995 distributor plug). But the thin white wire on the 1988-1991 harness goes where the thin white wire on the 1992-1995 harness went." ***This section needs further revisement for clarity, I will get to this before long...(KEW)***To clarify the information on the distributor wiring, match the like color wires at the distributor plugs (for example: org with org) and at the [ECU](/cars/electronics/ecu). In other words, the same color wire should go from distributor clear through to the [ECU](/cars/electronics/ecu). ###  Other assorted necessary items 

Fuel injectors: Model #4106 and #4107 fuel injectors were available for this swap from personal stock. The fuel injectors actually used were the #4107's, however it's not known what year these injectors were (either 93 or 94) as injectors from both years were available. The #4107 injectors were used because they worked with the 95 P28 [ECU](/cars/electronics/ecu) that was used and the #4106 injectors didn't though it isn't known why the #4106's didn't work. The utmost effort should be made to get injectors that match the P28 [ECU](/cars/electronics/ecu) to be used.
