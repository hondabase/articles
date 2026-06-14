---
summary: Archived JDM P30 D12 circuit modification for logging a 0-5 V analog input through the ECU.
applies_to:
  ecus: [P30]
  obd: [1]
complexity: advanced
tags: [ecu, datalogging, hardware, adc]
sources:
  - name: 'pgmfi.org wiki'
    title: 'Japanese Domestic Market P30D12 Modification'
    url: /pgmfi/wiki/library/japanese-domestic-market-p30d12-modification
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# JDM P30 D12 analog-input modification

This archived modification uses the otherwise-unused D12 input on a JDM OBD1 P30 ECU to log a 0-5 V analog signal, such as the output from an EGT thermocouple amplifier.

> [!WARNING]
> This procedure cuts or changes ECU-board circuits. The source reports successful tests on USDM and JDM P30 ECUs, but does not establish compatibility with other OBD1 ECUs. Verify the circuit and software behavior before modifying an ECU.

## USDM and JDM P30 differences

The original investigation used a USDM P30 for initial testing and a JDM P30 for the modification and its testing. It expected other Honda OBD1 ECUs to be similar, but did not confirm them.

| Detail | USDM P30 | JDM P30 |
| --- | --- | --- |
| D12 components | All installed | Some components missing |
| D12 circuit | Described as simpler | Described as more complex |
| D12 analog input | AI3, `66207` Pin 57 on the 64-pin DIP package | AI5, `66207` Pin 63 on the 68-pin PLCC package |
| Grounded analog input | AI5, `66207` Pin 59 | AI3, described as `66207` Pin 61 |
| High eight ADC bits | RAM `067h` | RAM `06Bh` |
| Remaining two ADC bits | Source describes the two most-significant bits of RAM `066h` as the ADC value's two least-significant bits | Source describes the two most-significant bits of RAM `06Ah` as the ADC value's two least-significant bits |

> [!NOTE]
> The archived JDM section twice uses "USDM" while describing the JDM circuit: it calls the grounded AI3 input part of a USDM P30 and calls the D12-to-AI5 path "USDM D12 circuitry." The table above follows the surrounding JDM context, but those labels were not independently corrected or verified.

![USDM P30 D12 input schematic](USDMP30D12Schematics.jpg)
*Archived schematic of the USDM P30 D12 circuit.*

## Archived JDM modification

The source says all of these changes are made on the back of the ECU board:

1. Replace `R15` with a diode.
2. Install another diode at `R14`. The source used surface-mount `1N-4148` diodes and described them as protection for the `66207` analog input.
3. Add a jumper across `R13`.
4. Add a jumper across the non-ground connections of `Q3` to carry D12 into the modified circuit.
5. Leave the `33 kohm` `R16` resistor and `C17` unchanged. The source did not identify `C17`'s value and said it appeared to be a tantalum capacitor.

![JDM P30 D12 circuit before and after modification](JDMP30D12CircuitEGTModR1.jpg)
*Archived before-and-after schematic for the JDM P30 D12 modification.*

![Modified JDM P30 board at the D12 and AI5 circuit](JDMp30D12ModPin63.JPG)
*Archived high-resolution photo of the modified JDM P30 board.*

The author tested both P30 variants with a `10 kohm` potentiometer used as a variable voltage divider across a 5 V supply, and with an EGADS EGT sensor. Those tests do not confirm other sensors or ECU variants.

## AI5 software caution

The archived page warns that OBD1 code appears to read AI5 and perform an unidentified function. Until that code was understood, it proposed a different, more invasive arrangement:

1. Cut the traces to both AI3 and AI5 at the `66207`.
2. Ground AI5.
3. Route the D12 circuit to AI3.

The source expected that pin swap to make a JDM ECU log D12 like a USDM ECU. It did not document the unknown AI5 function or provide broader validation, so treat this as an unverified historical proposal rather than a current recommendation.

## Related

- [Logging an external 0-5 V sensor through D12](/cars/electronics/how-to-log-external-data-such-as-an-egt-sensor)
- [Honda ECU datalogging overview](/cars/electronics/data-logging)
- [P30 ECU reference](/cars/electronics/p30)
