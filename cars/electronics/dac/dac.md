---
summary: 'Digital to Analog Converter. the process of taking a digital value and converting it to an analog signal of some variety.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
---

# DAC

Digital to Analog Converter. the process of taking a digital value and converting it to an analog signal of some variety. We'll use an 8-bit [DAC](/cars/electronics/dac) using a 5.00V reference as an example. The [DAC](/cars/electronics/dac) outputs a voltage (which can be measured with a DVM) ranging from (usually) zero output to the reference output, and is directly proportional to the input. `0x0` = 0V output. `0xff` (full scale in our example) = 5.00V output. General form: Vout = Vref * count / 2^n. Where 2^n is the number of bits in the converter. For our example we used an 8-bit converter, so 2^8 = 256 possible combinations. Zero is a valid value, consuming one of our combinations, so the total span is 0 - 255 counts. So redoing our general equation: Vout = 5.00V * count / 255 = 0.0196 * count. So this means that you can output any DC value to an accuracy of roughly 20mv. Pretty useful! Higher resolution [DAC](/cars/electronics/dac)s give more steps which allow better resolution. For example a 12-bit [DAC](/cars/electronics/dac) would give 1.22mv steps, 16 times better then the 8-bit part.
