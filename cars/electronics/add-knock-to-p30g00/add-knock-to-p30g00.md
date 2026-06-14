---
summary: "On 1720 or 11f0 I've: remove R140, R141 10k add R107, R115, R116 220R I also add (they may not be essential): C94 4u7 16v tant Q20 a143 On 1550150x: remove..."
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# Add Knock To P30G00

On 1720 or 11f0 I've: remove `R140`, `R141` - 10k add `R107`, `R115`, `R116` - 220R I also add (they may not be essential): `C94` - 4u7 16v tant `Q20` - a143 On 1550-150x: remove `R78`, `R77` (Reverse Side) add `R37` (RS), `R50` (RS), `R38` - marked 221 add `C82` - 4u7 16v tant You can convert a P75 to P30/72. The only ones I've seen use the 1550 board and no KS. I've converted one to p72 in the past. Is that a US one you have? I've also used a p29 1550 board and added KS, heated O2 and [DOHC](/cars/electronics/dohc) VTEC code.. for example. The KS board itself has been documented elsewhere in terms of tuning the KS frequency - I assume that's the `R12` and `R15` you refer to. The knock sensor frequency, and thus, its operation, is affected by the bore of the cylinder. From what I can tell, `each` [ECU](/cars/electronics/ecu)'s knock board is also dialed in to specific characteristics of the engine, to filter out engine noise from knock.. using a knock board with an engine other than it was designed for may not be very effective..
