---
summary: 'The J1 jumper on OBD1 ECUs controls the EA pin state, determining whether the MCU executes code from the internal program or an external ROM chip.'
tags: [ecu, tuning, rom, obd1, hardware]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# OBD1 ECU J1 Jumper Configuration

The **J1** jumper on OBD1 ECUs controls the state of the **EA** (External Access) pin on the MCU. This configuration determines whether the MCU executes code from its internal mask ROM or from an external ROM chip installed in the ECU.

## Technical Overview

The J1 jumper acts as a hardware switch for the MCU's boot mode. By pulling the EA pin to a specific logic level, the MCU is instructed to ignore its internal program memory and instead fetch instructions from the external memory socket.

> [!IMPORTANT]
> For any tuning application requiring a custom ROM chip (such as an SST27SF512 or similar), the J1 jumper must be installed (shorted). If J1 is left open, the ECU will attempt to boot from the internal mask ROM, which will result in a "Check Engine Light" or a failure to start when using modified maps.

## Configuration Reference

| Jumper State | EA Pin Logic | Boot Source |
| :--- | :--- | :--- |
| **Open** | High | Internal Mask ROM |
| **Shorted** | Low | External ROM (Socket) |

> [!TIP]
> When performing an ECU conversion for socketing, ensure the J1 jumper is bridged with a small piece of wire or a dedicated jumper pin. Verify continuity between the jumper pads and the corresponding MCU pin to ensure a reliable connection.

## Related Components

{{> resistor-color-codes }}