---
summary: 'See http://www.marklamond.co.uk/techhonda/pgmfi/o2input/o2input.htm for details this lets you modify you ECU for 05v input.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# O2 Input Mod

See [http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/o2-input.htm](http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/o2-input.htm) for details this lets you modify you ECU for 0-5v input. The [ADC](/cars/electronics/adc) is converts the analogue voltage of 0-5v in this case into a numerical representation of that voltage that the [CPU](/cars/electronics/cpu) can understand, and store in its memory. Notice I say 0-5v - this is because the [ADC](/cars/electronics/adc) is actually configured to read from 0-5v although the O2 input is processed so to limit the maximum voltage the [ADC](/cars/electronics/adc) sees to 3.8v. The most simple way to find out what the problem is would be to apply 5v onto the O2 input, and watch for it becoming altered along the route. That done it was discovered that the Op-Amp stage was limiting the voltage seen by the [ECU](/cars/electronics/ecu). This being the case I bypassed the op-amp by lifting a resistor and applied 5v directly to the Mux, and without much surprise we now see the [ECU](/cars/electronics/ecu) reading to 5v (or as close as it will ever get) - great stuff! ** From Marklamond's page ![standard-o2_small.gif](http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/standard-o2_small.gif)![modified-o2_small.gif](http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/modified-o2_small.gif)Real picture: Do this first: ![closeup_indexed_955.jpg](https://web.archive.org/web/http://forum.pgmfi.org/files/closeup_indexed_955.jpg)Then bend the CAP lead over and use it as a jumper, like this: ![bottom_jumpered_indexed_123.jpg](https://web.archive.org/web/http://forum.pgmfi.org/files/bottom_jumpered_indexed_123.jpg)
