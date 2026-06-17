---
summary: 'The NEC BACK0004 processor serves as a secondary backup controller in OBD0 MPFI ECUs, managing engine operation during limp mode.'
tags: [ecu, reference, sensors, diagnostics, obd0]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 NEC BACK0004 Processor Reference

The NEC BACK0004 processor is a secondary controller integrated into all OBD0 MPFI ECUs. Its primary function is to maintain engine operation when the primary ECU processor fails or enters a fault state, indicated by a solid red Check Engine Light (CEL) and the activation of Limp Mode.

## Functional Overview

The BACK0004 acts as a fail-safe mechanism. Under normal operating conditions, the primary ECU processor manages fuel injection, ignition timing, and sensor data. If the primary system detects a critical fault or experiences a hardware failure, the system transitions to Limp Mode.

> [!NOTE]
> When the BACK0004 is active, the engine will operate on a fixed, conservative map designed to allow the vehicle to reach a service location. Performance and fuel efficiency will be significantly reduced.

## Diagnostic Indicators

*   **CEL Status:** A solid red CEL indicates that the ECU has transitioned to its backup state.
*   **Limp Mode:** The engine will exhibit limited RPM ranges and fixed ignition timing.

## Technical Specifications

The BACK0004 is a dedicated integrated circuit found on the main logic board of OBD0 MPFI units. It operates independently of the main CPU to ensure that basic engine management functions remain active even if the primary processor is non-responsive.

> [!IMPORTANT]
> If the CEL is lit solid red, verify all primary sensor connections and ECU power grounds before assuming a failure of the BACK0004 or the primary processor.