---
summary: 'Convert OBD2P5M ECU from automatic to manual transmission by moving a 0-ohm SMD resistor from RP13 to RP14 on the PCB.'
tags: [ecu, conversion, tuning, wiring, transmission, modification]
complexity: beginner
---

# OBD2P5M Automatic to Manual Transmission Conversion

## Overview

This conversion requires moving a single 0-ohm SMD resistor on the PCB to reconfigure the ECU for manual transmission operation.

## Conversion Procedure

### Required Component

- **0-ohm SMD Resistor** — Identified by the `000` marking printed on the component.

### Steps

1. **Locate RP13** — Find the 0-ohm resistor at position RP13 on the underside (bottom) of the PCB.
2. **Remove the Resistor** — Carefully desolder the 0-ohm resistor from RP13 using appropriate SMD removal techniques.
3. **Install at RP14** — Solder the resistor to position RP14 on the top side of the PCB.

> [!IMPORTANT]
> Ensure the 0-ohm resistor is properly seated and all solder joints are secure before powering the ECU. Poor solder connections may cause intermittent electrical faults.

## Verification

After completing the resistor relocation, verify that:
- The resistor is firmly soldered at RP14.
- No solder bridges or cold joints are present.
- The ECU recognizes manual transmission operation during diagnostics.
