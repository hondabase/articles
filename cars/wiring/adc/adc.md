---
summary: 'Analog to Digital Converter: An integrated circuit (IC) which converts an analog signal to a digital representation.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion]
applies_to:
  obd: [0, 1, 2]
  brand: Acura
  models: [integra]
  chassis: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: ADC
    url: /pgmfi/wiki/library/adc
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ADC

Analog to Digital Converter: An integrated circuit (IC) which converts an analog signal to a digital representation. As an example let's consider an 8-bit [ADC](/cars/wiring/adc) with a 5.00V reference. 8-bit: An "8-bit [ADC](/cars/wiring/adc)" means that it will convert the input signal to an 2^8 equivalent numerical representation (that's where the "8" comes in.) 2^8 = 2*2*2*2*2*2*2*2 = 256 possible values. In the digital world, zero is a legitimate number, which uses up one of the possible combinations, giving us a 0-255 count output. 5.00V reference: The reference voltage is what the input signal is compared to, as a fraction. If we put a 5.00V signal into our [ADC](/cars/wiring/adc), and it's using a 5.00V reference, what will be the output? Full scale! In our 8-bit example "full scale" is 255 counts so that's what we get for the output. A zero signal input will output zero. Anyway the math works out to: Digital output = ((Vin / Vref) * 2^number of bits) - 1 With this you can find out exactly what your software will read from the [ADC](/cars/wiring/adc) with a given input signal. (For the purpose of this example I left out the case of measuring both positive and negative voltages, we won't see that in an automotive [ECU](/cars/ecu/ecu).) Analog to digital conversion is ***never*** perfect. It is a process of approximation - `each` ***exact*** digital value has to represent a ***range*** of analog values. The resolution (normally measured in bits) of an analog to digital converter represents how many possible values the analog range can be divided into.
