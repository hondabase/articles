---
summary: 'An overview of Analog-to-Digital Conversion (ADC) in automotive ECU applications, including resolution and reference voltage concepts.'
tags: [ecu, tuning, sensors, electronics-fundamentals]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Analog-to-Digital Conversion (ADC)

An **Analog-to-Digital Converter (ADC)** is a fundamental integrated circuit (IC) within an ECU that converts continuous analog voltage signals from engine sensors into discrete digital values that the ECU processor can understand and manipulate.

---

## Key Concepts

### Resolution (Bit Count)
The resolution of an ADC, measured in bits, determines the precision with which it can represent an analog signal. 

*   **Example (8-bit ADC):** An 8-bit converter divides the analog range into $2^8$ (256) possible values. 
*   **Counting:** In digital systems, counting typically starts at zero, resulting in a range of 0 to 255.

### Reference Voltage ($V_{ref}$)
The reference voltage defines the upper limit of the analog range the ECU can measure. If an ADC is using a 5.00V reference, an input signal of 5.00V will correspond to the "full scale" digital output (e.g., 255 in an 8-bit system).

---

## Conversion Calculation
The digital output value can be estimated using the following formula:

$$\text{Digital Output} = \left( \frac{V_{in}}{V_{ref}} \times 2^{\text{number of bits}} \right) - 1$$

*   $V_{in}$: Input signal voltage.
*   $V_{ref}$: Reference voltage.

### Precision and Approximation
Analog-to-digital conversion is an approximation process. Each digital value represents a specific range of analog voltages, not a single, perfectly precise point. Higher bit resolution allows for finer division of this analog range, reducing the error margin in sensor readings.
