yaml
---
summary: "PP5 ECU variants used in 1990–93 UK Rover 216 Cabrio and Honda Concerto models equipped with Honda ZC engines. Covers romless and external ROM configurations, Lambda sensor options, and cross-compatibility with PM-series ECUs."
tags:
  - pp5
  - ecu
  - obd0
  - rover
  - honda-concerto
  - zc-engine
  - romless
  - lambda-sensor
  - wiring
  - tuning
  - diagnostics
  - hardware
applies_to:
  obd:
    - 0
  brand: Honda
  vehicles:
    - Rover 216 Cabrio
    - Rover 216 GTi
    - Rover 220 Coupe
    - Honda Concerto 1.6L
complexity: intermediate
---

# PP5 ECU: Rover 216 Cabrio and Honda Concerto OBD0 Controller

## Overview

The PP5 is an OBD0 engine control unit used in 1990–1993 UK Rover vehicles equipped with Honda ZC-series engines. Rover maintained a licensing agreement with Honda that resulted in the integration of Honda powerplants into British-market Rover platforms while retaining OBD0 connector and distributor styles common to early 1990s Honda ECUs.

PP5 units are fundamentally similar in architecture to contemporary Honda ECU designs and share compatibility traits with PM6, PM7, and other OBD0 controllers.

## PP5 Variants and Applications

| **ECU Part Number** | **Vehicle Model** | **Engine Config** | **Lambda Sensor** | **Notes** |
|:---|:---|:---|:---|:---|
| PP5-E01 | Rover 216, 416 GTi | ZC (DOHC) | No | Romless; early production variant; difficult to reprogram |
| PP5-G01 | Rover 216 GTi | ZC (DOHC) | Yes | External ROM; common in UK market |
| PP5-R00 | Honda Concerto 1.6L | ZC (DOHC) | Yes | External ROM; 1993–96 model years |
| PP4-G01 | Rover 216 16V | ZC (SOHC) | Yes | External ROM; 1992–96 |
| PP4-R00 | Rover 220 Coupe; Honda Concerto 1.6L | ZC (SOHC) | Yes | External ROM; 1993–96 |

## Romless vs. External ROM Variants

### PP5-E01 (Romless)

The PP5-E01 was installed in early Rover 216, 416, and related models and **lacks onboard programmable ROM storage**. 

> [!CAUTION]
> PP5-E01 units are difficult to reprogram and require custom adapter hardware similar to PM6 and PM7 romless conversions. Reprogramming these units is not recommended for inexperienced users.

**Characteristics:**
- No integrated ROM; program logic stored in external masked ROM
- Typically found in Lambda-less configurations
- Requires specialized equipment for ECU reprogramming

### PP5-G01, PP4-G01, PP4-R00, PP5-R00 (External ROM)

These variants feature external, replaceable program ROM and are more common in the UK market.

**Characteristics:**
- Standard external ROM configuration
- Compatible with OBD0 diagnostic tools
- Support both Lambda-equipped and Lambda-less calibrations

## Cross-Compatibility and APS Sensor Considerations

PP5 ECUs are **OBD0 non-VTEC** units and are typically interchangeable with PM6, PM7, and equivalent Honda ECU families when:
- Connector pinout matches
- Engine management calibration is compatible with the target vehicle

> [!WARNING]
> Some PP5 variants incorporate an **APS (Atmospheric Pressure Sensor)** for altitude compensation. Vehicles equipped with APS-equipped ECUs will trigger **Check Engine Light (CEL)** or enter **Limp Mode** if the APS sensor is absent or disconnected.
>
> Verify APS requirement before ECU installation. Disable APS reading via tune if sensor is unavailable.

## Physical Documentation

```carousel
![PP5-E01 component side](PP5-E01-component.jpg)
*PP5-E01 upper PCB surface showing main IC layout and component placement*
<!-- slide -->
![PP5-E01 solder side](PP5-E01-solder.jpg)
*PP5-E01 lower PCB surface showing solder points and trace routing*
<!-- slide -->
![PP5-G01 variant](PP5-G01-variant.jpg)
*PP5-G01 external ROM variant; note ROM socket and pin configuration*
```

---

**Sources:** Technical documentation compiled from OBD0 ECU archives and UK Rover community reference materials.