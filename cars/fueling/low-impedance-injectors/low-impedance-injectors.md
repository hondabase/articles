---
summary: 'Technical guide to low-impedance (peak-and-hold) fuel injectors, inline resistor boxes, and converting between injector types on Honda engines.'
tags: [injectors, fueling, hardware]
applies_to:
  obd: [0, 1, 2]
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh, ek]
complexity: intermediate
---

# Low Impedance Injectors

Low-impedance injectors, also referred to as **peak-and-hold injectors**, have a very low internal coil resistance, typically between **2 and 6 ohms** (most commonly 2.5 to 3 ohms on vintage Honda setups).

## Overview

Unlike saturated circuits, peak-and-hold injectors are designed to open as fast as possible. Because of their low coil resistance, they allow a large amount of current to flow through the circuit when 12V is applied. 

To control this current, true peak-and-hold ECU drivers use a two-stage current profile:
1. **Peak Phase:** The ECU hits the injector with a high current pulse (around 4 amps) to snap the heavy internal pintle open quickly.
2. **Hold Phase:** Once open, the ECU reduces the current to a lower holding level (around 1 amp) to keep the valve open for the remainder of the pulse width.

> [!WARNING]
> If you connect low-impedance injectors directly to a standard saturated driver (found in most OBD1/OBD2 Honda Civic and Integra ECUs) without current limitation, the excessive current flow will overheat and burn out the ECU's internal driver transistors within minutes.

## The Resistor Box Solution

To safely run low-impedance injectors on an ECU designed for high-impedance (saturated) injectors, you must install an **inline resistor box** (also called a resistor pack).

The resistor box adds approximately **6 to 10 ohms** of resistance in series with each injector's power supply wire. This raises the total circuit resistance to around 10–13 ohms, mimicking a high-impedance injector. This limits the current to a safe level (~1.2 amps) and protects the ECU drivers, though it sacrifices a small amount of the opening speed advantage of a true peak-and-hold driver circuit.

## Specifications

| Engine / Vehicle | OBD Generation | Flow Rate (cc/min) | Nominal Resistance | Factory Resistor Box? |
| :--- | :---: | :---: | :---: | :---: |
| **D16A6 (CRX/Civic Si)** | OBD0 | 240cc | ~2.5 ohms | Yes |
| **B16A (JDM EF8/EF9)** | OBD0 | 240cc | ~2.5 ohms | Yes |
| **H22A1 (Prelude VTEC)** | OBD1 | 345cc | ~2.5 ohms | Yes |

## Resistor Box Wiring Reference

An OEM Honda resistor box has **5 wires**:

* **1 Power Wire (Red):** Receives +12V switched power from the main relay.
* **4 Output Wires (Black):** Connect to the power side of each of the four fuel injectors.

```text
 +12V Switched Power (from Main Relay)
 |
 [ Resistor Box ]
 (Red Wire)
 / | \ \
 [10Ω] [10Ω] [10Ω] [10Ω] (Internal Resistors)
 / | \ \
 (Black) (Black) (Black) (Black) (Output Wires)
 | | | |
 [Inj 1] [Inj 2] [Inj 3] [Inj 4]
 | | | |
 (To ECU Ground Trigger Pins A1, A3, A5, A2)
```

## Installation Procedure

### Wiring a Resistor Box into a Saturated Harness

1. **Locate the Injector Power Joint:** In a factory saturated harness, all four injectors share a common +12V power source wire (usually Yellow/Black) that splits near the intake manifold.
2. **Cut the Power Wires:** Cut the individual Yellow/Black power wires going to each injector plug. Leave the ground return wires (which go to the ECU) untouched.
3. **Mount the Box:** Mount the aluminum resistor box securely to the firewall.
4. **Connect Switched Power:** Connect the single **Red wire** of the resistor box to the main +12V switched power source wire coming from the vehicle harness.
5. **Connect Outputs:** Connect the **four Black wires** of the resistor box to the injector-side of the cut Yellow/Black power wires (one Black wire to each injector).
6. **Solder and Insulate:** Solder all connections and insulate them with marine-grade adhesive-lined heat shrink tubing to protect them from engine bay moisture.

> [!TIP]
> Ensure all connections are soldered and heat-shrunk. Crimp connectors are prone to corrosion and failure in the high-heat, high-vibration environment of the engine bay.