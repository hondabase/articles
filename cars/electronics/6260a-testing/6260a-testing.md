---
summary: "J. Wong: about the 6260A thing... if you take a look at the code (91 PM6ECULEDCEL) that flashes the ECU LED for codes you'll see that it writes 16 or 96 to X2000, depending on certain conditions."
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - diagnostics
---

# 6260A Testing

J. Wong: about the 6260A thing... if you take a look at the code ([91 PM6_ECU_LED_CEL](/cars/electronics/91pm6-ecu-led-cel)) that flashes the [ECU](/cars/electronics/ecu) LED for codes you'll see that it writes #16 or #96 to X2000, depending on certain conditions. A bench experiment i want to do is to replace 16/96 with other values and see what happens... like instead of the led flashing, observe what other line would toggle
