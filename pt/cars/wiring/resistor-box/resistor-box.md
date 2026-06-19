---
summary: 'Instructions for wiring a Resistor Box to use Peak and Hold injectors with OBD systems.'
tags: [ecu, injectors, peak-and-hold, resistor-box, wiring, conversion]
complexity: advanced
---

# Resistor Box Wiring for Peak and Hold Injectors

A Resistor Box is a passive circuit component that enables the use of Peak and Hold (high-impedance) injectors with ECUs designed for low-impedance injector operation. This guide covers wiring, installation, and configuration.

## Overview

Peak and Hold injectors require a different electrical approach than standard low-impedance injectors. The Resistor Box manages the voltage and current characteristics to allow compatibility across OBD0, OBD1, and OBD2 systems.

> [!IMPORTANT]
> Improper Resistor Box wiring can result in injector failure, ECU damage, or engine control loss. Verify all connections before engine start.

## Components and Specifications

| Component | Function | Notes |
|-----------|----------|-------|
| Resistor Box | Converts ECU output for Peak and Hold injectors | Manages peak vs. hold current phases |
| Resistors | Primary and hold-phase resistance | Values vary by injector impedance |
| Diode | Prevents reverse voltage spike | Required for injector coil protection |
| Capacitor | Smooths voltage transients | Optional, recommended for stability |

## Wiring Configuration

### Basic Connection Diagram

**ECU Injector Output → Resistor Box Input**
- Connect the ECU's injector output signal wire to the Resistor Box input terminal
- Connect the Resistor Box output to the injector coil positive terminal
- Ground the injector negative terminal directly to engine ground

### Pin Assignments

| Pin | Signal | Destination | Wire Color |
|-----|--------|-------------|-----------|
| Input | ECU Injector Output | Resistor Box In | Typically green/white |
| Output | Injector Control | Injector Positive | Varies by application |
| Ground | Chassis Ground | Engine/Battery Ground | Black |

## Installation Steps

1. **Disconnect the battery** at the negative terminal to prevent electrical faults during wiring.

2. **Locate the ECU injector output wires** on your specific OBD variant.

3. **Install the Resistor Box** in an accessible location, preferably near the ECU or engine bay relay cluster.

4. **Connect input wire** from ECU injector terminal to Resistor Box input.

5. **Connect output wire** from Resistor Box to injector coil positive terminal.

6. **Verify ground paths:**
   - Confirm low-resistance connection from injector negative to engine block
   - Test continuity with a multimeter (target: <0.5Ω)

7. **Reconnect the battery** and verify injector operation via fuel pressure observation or injector clicking test.

> [!TIP]
> Install an inline 15A fuse between the Resistor Box output and injector harness for additional protection against short-circuit conditions.

## OBD-Specific Considerations

### OBD0 Systems
- Single injector output per cylinder bank
- Resistor Box must handle full peak current for paired injectors
- Verify ECU pulse width capability before installation

### OBD1 Systems
- Typically four independent injector channels
- One Resistor Box per injector or one shared unit with distribution harness
- Check ECU maximum output current rating

### OBD2 Systems
- Integrated multi-point fuel injection with dedicated drivers
- Some OBD2 ECUs have native Peak and Hold capability; verify before adding Resistor Box
- Verify fuel injector impedance specifications

## Testing and Verification

> [!CAUTION]
> Do not operate the engine for extended periods without verifying proper injector function. Overheating or flooding may result.

1. **Injector Resistance Check:**
   - Measure coil resistance with multimeter (ohms setting)
   - High-impedance Peak and Hold: 12–16Ω
   - Low-impedance standard: 2–4Ω
   - Document baseline for future comparison

2. **Fuel Pressure Observation:**
   - Start engine and observe fuel pressure gauge
   - Should stabilize within 35–45 psi (OBD0/1) or 45–60 psi (OBD2)
   - Pressure oscillation indicates proper injector pulsing

3. **Idle Quality:**
   - Engine should start and idle smoothly
   - No rough idle, hesitation, or stalling
   - Check for diagnostic trouble codes via OBD scanner

4. **Load Testing:**
   - Gradually increase throttle and observe throttle response
   - No bogging, hesitation, or fuel starvation symptoms
   - Monitor for injector chatter or clicking via stethoscope (normal)

## Troubleshooting

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Engine won't start | Injector not pulsing | Verify ECU output signal with oscilloscope; check Resistor Box continuity |
| Rough idle | Inconsistent fuel delivery | Inspect injector spray pattern; test fuel pressure regulator |
| No fuel pressure | Fuel pump or injector blockage | Check fuel filter; run injector cleaner; bench-test injectors |
| Overheating Resistor Box | Continuous high current draw | Verify injector impedance; check for short circuit; reduce pulse width |

## Safety Precautions

> [!WARNING]
> Always disconnect the battery before modifying fuel system wiring. Accidentally triggering the fuel pump relay can pressurize the fuel system and create fire hazard.

- Ensure all connections are crimped and soldered (no wire nuts in fuel system circuits)
- Use appropriate wire gauge for current capacity (typically 16–18 AWG for injector circuits)
- Install fuses inline on positive conductors
- Do not run wiring near exhaust manifolds or moving engine components
