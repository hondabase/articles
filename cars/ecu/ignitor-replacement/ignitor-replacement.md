---
summary: 'Replace the internal Honda distributor ignitor with a solid-state circuit to provide a clean trigger signal for aftermarket ignition systems like MSD or Crane.'
tags: [ignition, distributor, wiring, msd, upgrade]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Honda Distributor Ignitor Replacement for Aftermarket Ignition

This modification replaces the factory Honda ignitor module with a solid-state circuit. This setup is designed to provide a clean, reliable trigger signal for aftermarket ignition boxes, such as MSD or Crane units.

## Technical Overview

The factory ignitor is replaced by a transistor-based circuit that mimics the switching behavior required by aftermarket ignition controllers. 

> [!NOTE]
> The ZTX857 transistor is recommended due to its physical size, which allows it to fit within the distributor housing. However, any power Darlington NPN transistor capable of handling the required current (typically 2+ amps) is a suitable substitute.

## Schematic

![Honda to MSD Ignition Trigger Schematic](HondaToMSD.gif)

## Implementation Details

When building the circuit, ensure all connections are heat-resistant and vibration-proof, as the distributor environment is subject to high temperatures and constant mechanical stress.

> [!CAUTION]
> Ensure the transistor is properly insulated from the distributor housing if it is mounted to the metal casing to prevent short circuits. Use thermal paste if mounting to a heat sink surface to ensure longevity.

> [!TIP]
> Verify the trigger voltage requirements of your specific aftermarket ignition box (e.g., MSD 6A/6AL) to ensure the circuit output matches the controller's input specifications.
