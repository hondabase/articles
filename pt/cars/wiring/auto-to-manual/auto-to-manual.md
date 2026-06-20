---
summary: 'Convert automatic transmissions to 5-speed manual ECU configurations on Honda/Acura vehicles. Most automatic ECUs can be converted via software ROM modification or hardware changes with minimal additional components.'
tags: [ecu, transmission, auto-to-manual, conversion, rom, tuning, wiring, hardware-modification, diagnostics]
applies_to:
  make: [Acura, Honda]
complexity: intermediate
---

# Automatic to Manual ECU Conversion

## Overview

Most Honda/Acura automatic ECUs can be converted to control 5-speed manual transmissions with straightforward modifications. Reverse conversions (manual to automatic) typically require additional hardware components.

Conversions can be accomplished via **software (ROM modification)** or **hardware changes**:

- **Software Approach:** Modified ROM images (e.g., "Mugen" variants) disable automatic transmission hardware checks, allowing an automatic ECU to control a manual 5-speed engine without generating Code 19 (automatic transmission lockup solenoid error).
- **Hardware Approach:** Physical circuit modifications can be made to trick an automatic ECU into operating as a manual unit. This method is highly specific to each ECU variant.

> [!TIP]
> Software-based conversions are generally simpler and require no soldering or component removal.

## OBD0 Automatic to Manual Conversions

### OBD0 Automatic to Manual Without Hardware Removal

Control a manual 5-speed transmission using an automatic OBD0 ECU without triggering the Check Engine light.

**Related Article:** [OBD0 ECU Automatic to Manual Without Removing Any Hardware](/cars/wiring/obd0ecuautotomanualwithoutremoveanyhardware)

### PS9, PG7, PM7, PR5 Automatic to Manual

Convert automatic PS9, PG7, PM7, or PR5 OBD0 circuit boards into a manual PM6-style ECU.

**Related Article:** [PS9 Automatic to Manual](/cars/sensors/ps9-auto-manual)

### PR4 OBD0 Automatic to Manual

Convert a PR4 OBD0 automatic ECU to manual configuration.

**Related Article:** OBD0 PR4 Automatic to Manual

### PR3 Automatic to Manual

Convert a PR3 automatic ECU to manual operation.

**Related Article:** [PR3 Automatic to Manual](/cars/ecu/pr3-auto-manual)

## OBD1 Automatic to Manual Conversions

### Civic & Integra Automatic to Manual (1992–1995)

Convert automatic ECUs from 1992–1995 Civic and Integra models to manual transmission control.

**Related Article:** [OBD1 Civic Integra Automatic to Manual](/cars/wiring/obd1-civic-integra-auto-manual)

### P08 & P30 Automatic to Manual (JDM Mini-Style)

Convert JDM automatic P08 or P30 (mini-style) ECUs to manual configuration.

**Related Article:** [OBD1 P08 Automatic to Manual](/cars/honda/civic/eg/sensors/obd1p08-auto-manual)

### P13 Prelude H22A Automatic to Manual (1992–1995)

Convert Prelude H22A automatic ECUs from 1992–1995 to manual transmission control.

**Related Article:** [OBD1 P13 Automatic to Manual](/cars/wiring/obd1p13-auto-manual)

## OBD2 Automatic to Manual Conversions

### P5M Prelude H22A Automatic to Manual (1997–2001)

Convert Prelude H22A PCM units from 1997–2001 from automatic to manual transmission operation.

**Related Article:** [OBD2 P5M Automatic to Manual](/cars/wiring/obd2p5m-auto-manual)
