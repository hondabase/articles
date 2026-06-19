---
summary: 'Technical overview of the PS9 ECU used in 1990-1991 USDM Honda Civic EX models, featuring integrated automatic transmission control.'
tags: [ecu, obd0, honda, ps9, transmission]
applies_to:
  models: ['Civic EX']
  chassis: [EF]
complexity: beginner
---

# PS9 ECU Technical Overview

The PS9 ECU was utilized in 1990–1991 USDM Honda Civic EX models equipped with the 1.6L SOHC engine. 

> [!NOTE]
> The PS9 hardware architecture is functionally identical to the PM6 ECU, with the addition of dedicated circuitry required to manage an automatic transmission.

## Hardware Specifications

The PS9 is primarily distinguished by its integrated transmission control unit (TCU) functionality. When servicing or tuning this unit, refer to the following comparison:

| Feature | PM6 | PS9 |
| :--- | :--- | :--- |
| **Engine Compatibility** | 1.6L SOHC | 1.6L SOHC |
| **Transmission Control** | Manual | Automatic |
| **Architecture** | OBD0 | OBD0 |

## Technical Documentation

The following image provides a visual reference for the PS9 PCB layout and component identification.

![PS9 ECU PCB](PS9auto.jpg)
*Digital scan of the USDM PS9 automatic ECU PCB*

> [!IMPORTANT]
> Ensure all modifications to the PS9 board are performed using appropriate ESD-safe equipment. Because the PS9 shares the same base architecture as the PM6, standard OBD0 tuning procedures apply, provided the transmission control logic remains undisturbed.
