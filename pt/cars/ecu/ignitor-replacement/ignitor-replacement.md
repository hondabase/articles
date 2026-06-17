---
summary: 'Learn how to replace the internal Honda distributor ignitor with a solid-state circuit to trigger aftermarket ignition systems like MSD or Crane.'
tags: [ecu, ignition, wiring, distributor]
applies_to:
  obd: [0, 1, 2]
  models: [Honda]
complexity: beginner
---

# Honda Distributor Ignitor Replacement for Aftermarket Ignition

The internal Honda ignition module (ignitor) can be bypassed or replaced with a solid-state circuit to provide a clean trigger signal for aftermarket ignition boxes, such as MSD or Crane systems.

## Overview
This modification allows the ECU to trigger an external ignition controller directly, bypassing the high-current switching requirements of the factory ignitor.

> [!NOTE]
> The ZTX857 transistor is not a strict requirement. Any NPN Darlington power transistor capable of handling the necessary current load can be used as a substitute.

## Circuit Diagram

![Honda to MSD Ignition Trigger Circuit](HondaToMSD.gif)
*Schematic for solid-state ignitor replacement*

## Implementation Details
To interface the Honda ECU signal with an aftermarket ignition box:

1. **Transistor Selection:** Ensure the chosen NPN Darlington transistor is rated for the current requirements of the ignition trigger input.
2. **Wiring:** Connect the circuit according to the schematic above, ensuring proper grounding to the distributor housing or chassis to prevent signal noise.
3. **Compatibility:** This setup is compatible with most capacitive discharge ignition (CDI) systems that accept a standard square-wave trigger signal.

> [!WARNING]
> Ensure all connections are soldered and heat-shrunk to prevent vibration-induced failure within the distributor environment. Improper wiring may result in a no-start condition or damage to the ECU ignition output stage.