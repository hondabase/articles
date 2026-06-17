---
summary: 'Step-by-step instructions for socketing and chipping small-case Honda OBD1 ECUs, commonly found in JDM and some European models.'
tags: [ecu, chipping, obd1, tuning]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# Chipping OBD1 Small-Case ECUs

Small-case OBD1 ECUs, commonly found in JDM and European market vehicles, require specific considerations for socketing and chipping compared to standard North American large-case units.

> [!IMPORTANT]
> Ensure you have verified the PCB revision before beginning the socketing process, as trace layouts may vary between specific small-case board variants.

## Required Components
*   28-pin DIP socket (machined pins recommended)
*   29C256 or 27SF512 EEPROM chip
*   74HC373 latch (if not already present on the board)
*   1k ohm resistor (for J1 jumper)

## Procedure
For detailed step-by-step instructions on the physical modification process, refer to the [Chipping JDMP30](/cars/rom/chipping-jdmp30) guide.

## Board Overview

```carousel
![Top view of small-case PCB](p30mtat2.jpg)
*Top view of the small-case ECU PCB layout*
<!-- slide -->
![Underside of small-case PCB](p30_ecu_underside.jpg)
*Underside of the PCB showing solder points and trace routing*
<!-- slide -->
![Detailed view of ECU components](p30mtat1.jpg)
*Close-up of the primary ECU component cluster*
```

> [!TIP]
> Use a high-quality desoldering station to remove factory solder from the ROM location to prevent damage to the through-hole plating.