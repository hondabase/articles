yaml
---
summary: "Easily enable O2 sensor heater functionality on ECUs lacking the circuit, such as P05 models, by adding a single transistor component."
tags: [ecu, o2-sensor, heater, wiring, transistor, conversion, obd-codes]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# O2 Sensor Heater Circuit Retrofit

## Overview

ECUs lacking an O2 sensor heater circuit—such as P05 and P08 models—can be retrofitted with this functionality by adding a single transistor. Without the heater circuit, the ECU will generate a fault code. This guide covers the retrofit procedure for both USDM and JDM variants.

> [!IMPORTANT]
> Adding the heater circuit transistor is required to prevent O2 sensor heater fault codes on ECUs that lack factory implementation.

## Required Components

| Component | Designation | Part Number | Notes |
|-----------|-------------|------------|-------|
| NPN Switching Transistor (SMD) | Q30 or Q15 | MMBT4401 or C144 | 2N4401 equivalent |

## P05 ECU Retrofit

**Location:** Q30 on the main PCB

1. Identify transistor location Q30 on the ECU board.
2. Install an NPN switching transistor (part number C144 or equivalent 2N4401).
3. Verify solder connections for continuity before reinstalling the ECU.

> [!TIP]
> The C144 designation is the OEM equivalent to a standard 2N4401 transistor.

## P08 (JDM) ECU Retrofit

**Location:** Q15 on the bottom of the PCB

1. Locate position Q15 on the underside of the board.
2. Install a surface-mount (SMT) variant of the 2N4401 transistor (MMBT4401).
3. Verify component orientation: emitter (E), base (B), and collector (C) must align with board markings.

> [!NOTE]
> MMBT4401 components are readily available through standard electronics distributors such as Digi-Key.

## Verification

After installation, perform the following checks:

- **Visual Inspection:** Confirm solder joints are clean and free of bridges.
- **Continuity Test:** Verify transistor pins are properly connected using a multimeter.
- **Fault Code Clear:** Erase any existing O2 sensor heater fault codes after installation.

> [!CAUTION]
> Improper transistor installation or orientation may result in circuit damage or continued fault codes. Double-check component polarity before soldering.