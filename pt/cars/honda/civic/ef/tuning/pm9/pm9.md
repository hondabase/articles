---
summary: 'The PM9 is essentially a variant of the PM5 ECU, with differences primarily related to transmission type (4-speed vs. 5-speed) and processor architecture across model years.'
tags: [ecu, pm9, pm5, reference, tuning, sensors, processor]
applies_to:
  brand: Honda
complexity: advanced
---

# PM9 ECU

## Overview

The PM9 is essentially a variant of the [PM5](/cars/honda/civic/ef/tuning/pm5) ECU. The PM5 and PM9 are fundamentally the same ECU platform, with primary differences related to transmission type and processor generation across model years.

> [!IMPORTANT]
> PM5 and PM9 units employ two distinct processor designs similar to the [PG7](/cars/sensors/pg7). Early models (1988–1989) use an `83C154` processor, while later models (1990–1991) use a `66201` processor. The 1990–1991 processor configuration closely resembles OBD1 ECU architecture.

## Variants and Transmission Compatibility

| **Model Year(s)** | **Processor** | **Transmission** | **Notes** |
| :--- | :--- | :--- | :--- |
| 1988–1989 | 83C154 | 4-speed / 5-speed | Earlier design variant |
| 1990–1991 | 66201 | 4-speed / 5-speed | OBD1-style processor layout |

The PM9 units documented were sourced from Honda Civic HF models with 4-speed transmissions, suggesting a potential correlation between ECU variant and transmission type, though this relationship is not definitively confirmed.

## Physical Reference Images

```carousel
![PM9 top view](pm9top.jpg)
*PM9 ECU – top side showing processor and main components*
<!-- slide -->
![PM9 bottom view](pm9bottom.jpg)
*PM9 ECU – bottom side showing solder points and trace routing*
```

## Related References

- [PM5 ECU](/cars/honda/civic/ef/tuning/pm5)
- [PG7 Sensors](/cars/sensors/pg7)
- [OBD Wiring Standards](/cars/wiring/obd)
