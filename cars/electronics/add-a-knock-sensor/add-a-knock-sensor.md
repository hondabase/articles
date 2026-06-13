---
summary: 'Adding a knock sensor to an engine that did not come with one.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - knock
  - sensor
  - wiring
---

# Add A Knock Sensor

To add a Knock Sensor to a P75 here is what I did:

1. Remove a knock board from a JDM p30
2. Move the connector strip from prot "A" to port "B"
3. Remove R12
4. Add R15 and R11 (both 100 ohm... you can re-use R12)
5. Solder it to the p75/p72 conversion at location FC1

That's it. If you've already converted the p75 to a p72 then you now have a 100% functional p72 board. Go ahead and enable the knock sensor in your p72 code and have fun!! -Andrew Note: I salvaged a scrap JDM ECU from a junk yard and the process for using a JDM P72 Knock board is the same, with the exception of moving the connector strip from Connector port B to Connector port A. I believe this was what Andrew was trying to say above, just a minor typo methinks? -S\_K
