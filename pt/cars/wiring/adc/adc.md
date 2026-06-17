yaml
---
summary: "An analog-to-digital converter (ADC) is an integrated circuit that converts analog signals into digital representations. Learn ADC fundamentals, bit resolution, reference voltage, and conversion mathematics."
applies_to:
  obd: [0, 1, 2]
  brand: Acura
complexity: intermediate
tags:
  - adc
  - ecu
  - sensors
  - conversion
  - wiring
  - tuning
  - reference
---

# Analog-to-Digital Converter (ADC)

An analog-to-digital converter (ADC) is an integrated circuit that converts analog input signals into digital representations. Understanding ADC operation is essential for sensor signal interpretation and ECU tuning.

## ADC Fundamentals

### Bit Resolution

The bit resolution of an ADC determines how many discrete values it can represent. An 8-bit ADC produces 2^8 = 256 possible output values (0–255).

**Calculation:**
- 2^8 = 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 = 256 values
- Range: 0 to 255 (zero is a valid state)

### Reference Voltage

The reference voltage (Vref) is the maximum analog input that corresponds to full-scale digital output. A common reference voltage in automotive ECUs is 5.00V.

**Example:**
- If Vref = 5.00V and the input signal = 5.00V, the output = 255 (full scale)
- If the input signal = 0V, the output = 0

## Conversion Formula

The digital output is calculated as:

**Digital Output = ((Vin / Vref) × 2^number of bits) − 1**

Where:
- **Vin** = Input analog voltage
- **Vref** = Reference voltage
- **Number of bits** = ADC resolution (e.g., 8, 10, 12 bits)

This formula allows precise prediction of the digital value the ECU will read for any given input signal.

## Resolution and Accuracy

> [!IMPORTANT]
> Analog-to-digital conversion is inherently an approximation process. Each discrete digital value must represent a range of analog values, not a single point.

**Resolution** (measured in bits) defines how finely the ADC divides the analog input range:

- **Higher bit resolution** = Smaller steps between values = Greater precision
- **Lower bit resolution** = Larger steps between values = Lower precision

For example, an 8-bit ADC with a 5.00V reference has a step size (least significant bit, or LSB) of:
- LSB = Vref / 2^bits = 5.00V / 256 ≈ 0.0195V per step

An 10-bit ADC with the same 5.00V reference provides finer resolution:
- LSB = 5.00V / 1024 ≈ 0.00488V per step