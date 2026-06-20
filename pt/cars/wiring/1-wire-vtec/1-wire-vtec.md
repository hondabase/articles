---
summary: '1 Wire VTEC is a ROM modification for OBD0 MPFI ECUs that repurposes the automatic transmission lockup solenoid to control VTEC activation.'
tags: [ecu, rom, tuning, vtec, solenoid, wiring, conversion, obd0]
complexity: beginner
---

# 1 Wire VTEC

## Overview

1 Wire VTEC is a ROM modification for OBD0 MPFI ECUs that repurposes the automatic transmission lockup solenoid to control VTEC activation. This approach eliminates the need for dedicated VTEC wiring by utilizing an existing solenoid output on automatic transmission-equipped vehicles.

> [!NOTE]
> This implementation has been functional since October 2003 and is currently in use on multiple vehicles. Community testing and feedback continue to help refine the system.

## Hardware Requirements

To implement 1 Wire VTEC, you will need:

- OBD0 MPFI ECU (compatible models listed below)
- Automatic transmission lockup solenoid
- Associated wiring harness modifications
- Flashed ROM with 1 Wire VTEC code

> [!IMPORTANT]
> Refer to the [hardware modifications guide](/cars/sensors/hardware-for-one-wire-vtec) for detailed installation and wiring specifications.

## System Operation

The 1 Wire VTEC system works by:

1. Reading the stock VTEC activation conditions from the modified ROM
2. Sending the VTEC engagement signal through the automatic transmission lockup solenoid output
3. Triggering VTEC solenoid activation based on programmed engine parameters (RPM, load, throttle position)

## Compatibility

This modification is compatible with:

- **OBD0 MPFI ECUs** with automatic transmission solenoid outputs
- Vehicles using Honda's original VTEC solenoid hardware

> [!WARNING]
> Manual transmission vehicles or ECUs without an automatic transmission lockup solenoid output cannot use this implementation. Verify your ECU variant before proceeding.

## Development and Support

The 1 Wire VTEC project maintains an active codebase under the `1w_vtec` module. Community contributions, vehicle testing, and additional refinements are ongoing.

For involvement with the project, consult the official source repository for the latest code and documentation.

## See Also

- [OBD0 MPFI Diagnostics](/cars/diagnostics/obd0mpfi)
- [ROM Modifications](/cars/tuning/rom)
- [ECU Hardware](/cars/ecu/ecu)
- [Automatic Transmission Lockup Solenoid](/cars/sensors/automatic-transmission-lockup-solenoid)
