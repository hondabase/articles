---
summary: 'The EA (EA Prime) pin on the MCU determines whether the ECU executes code from internal ROM or an external ROM chip, essential for tuning and chip modification.'
tags: [ecu, reference, tuning, mcu]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# EA (EA Prime) Pin Functionality

The **EA** (External Access) pin, often referred to as **EA Prime**, is a control pin on the MCU that dictates the memory source for the processor. It determines whether the MCU executes instructions from its internal ROM or an external ROM chip.

## Technical Overview

On standard 40-pin Intel 8051-based MCUs used in OBD1 ECUs, the EA pin is located at **Pin 31**. 

*   **Logic High:** The MCU executes code from the internal ROM.
*   **Logic Low:** The MCU ignores internal ROM and executes code from an external ROM chip.

> [!IMPORTANT]
> In the context of OBD1 ECU modification, the **J1** jumper is used to control the state of the EA pin. When J1 is bridged, it pulls the EA pin low, allowing the MCU to access the external ROM chip installed on the ECU board.

## Pin Configuration

| Component | Pin Location | Function |
| :--- | :--- | :--- |
| **MCU** | Pin 31 | External Access (EA) control |
| **Jumper** | J1 | Toggles EA state (Internal vs. External) |

> [!TIP]
> Always verify the J1 jumper configuration when installing an aftermarket chip or daughterboard, as the MCU will fail to boot from the external ROM if the EA pin is not correctly pulled low.
