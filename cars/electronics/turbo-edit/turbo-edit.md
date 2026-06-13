---
summary: 'An introduction to TurboEdit, the free open-source ROM editing and tuning software for OBD0 Honda ECUs (PM6/PM7 codebases).'
applies_to:
  obd: [0]
complexity: intermediate
tags:
  - tuning
  - rom
  - software
---

# Introduction to TurboEdit (OBD0 Honda Tuning)

TurboEdit is a free, open-source ROM editing and tuning software suite designed specifically for first-generation Honda OBD0 Multi-Point Fuel Injection (MPFI) Engine Control Units (ECUs). It is the primary platform used to tune 1988–1991 Honda Civic and CRX models without converting the vehicle's chassis wiring to newer OBD1 standards.

---

## 1. Supported ECUs and Codebases

TurboEdit targets the OKI-based microcontrollers found in OBD0 Honda ECUs:

- **PM6:** The USDM ECU sourced from the 1988–1991 Civic/CRX Si (equipped with the SOHC D16A6 engine).
- **PM7 / PP5:** Sourced from JDM and European DOHC ZC-equipped models.

Because stock OBD0 ECUs were never designed to handle boost or real-time communication, TurboEdit relies on custom-patched ROM codebases (most notably the **NG69** and **NG22** codebases). These patches rewrite sections of the factory code to add support for forced induction, larger injectors, and serial datalogging.

---

## 2. Key Features of TurboEdit

TurboEdit transforms a standard OBD0 ECU into a fully programmable engine management system:

### MAP Sensor Scaling
Stock Honda MAP sensors only read up to atmospheric pressure (1-bar). TurboEdit allows you to scale the map pressure columns (MAP scalers) to support aftermarket 2-bar or 3-bar MAP sensors (such as GM or Motorola sensors), enabling the ECU to calculate fuel and timing under boost.

### Boost Retard Calibration
Under forced induction, ignition timing must be retarded to prevent knock. TurboEdit allows tuners to define a timing retard slope (e.g., pulling 0.75° of timing per psi of boost) as pressure climbs into positive load columns. Refer to the [ignition timing guide](/cars/electronics/tuning-timing) for safe retard guidelines.

### Fuel Multiplier Adjustment (Injector Scaling)
The OBD0 ECU calculates fuel delivery using an 8-bit map value and a column-specific multiplier. When upgrading to larger fuel injectors (such as standard DSM 450cc injectors), the factory multipliers will dump too much fuel. TurboEdit allows you to adjust these fuel multipliers to scale the entire fuel map down, matching the flow rate of larger injectors.

### Real-Time Programming (RTP)
With hardware emulators (such as the Moates Ostrich or Xtronics Pocket ROMulator) plugged into the ECU's 28-pin ROM socket, TurboEdit allows you to modify fueling, timing, and rev limits on the fly while the engine is running.

---

## 3. Common OBD0 Tuning Troubleshooting

When tuning with TurboEdit, be aware of these common OBD0 hardware limitations:

- **Solid Check Engine Light (Limp Mode):** Modifying any byte on the ROM changes its checksum. If you do not apply the checksum bypass patch (changing the checksum byte at address `20B2` on [PW0 ECUs](/cars/electronics/pw0) or the corresponding location on PM6 ECUs), the ECU will throw a solid CEL and enter limp-home mode.
- **Datalogging Signal Noise:** OBD0 ECUs do not have a dedicated buffer chip on the serial lines like OBD1 ECUs. Datalogging signals are highly sensitive to electrical noise from spark plug wires. Always route your serial cables away from the distributor and spark plugs.

## Related Articles
- [Honda OBD Generations Overview](/cars/electronics/obd)
- [How to Interpret Fuel and Ignition Maps](/cars/electronics/understanding-maps)
- [Baseline Targets for Fuel and Ignition Timing](/cars/electronics/ecu-tuning)
