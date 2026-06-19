---
summary: 'Overview of the Honda Fuel Injector Test Circuit, its function in USDM ECUs, and how it relates to Diagnostic Trouble Code 16.'
tags: [ecu, fuel-injection, diagnostics, obd, reference]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda Fuel Injector Test Circuit

The **Injector Test Circuit** is a diagnostic feature found in many **USDM (United States Domestic Market)** Honda ECUs. Its primary purpose is to verify the electrical connection between the ECU and the fuel injectors.

If the ECU detects a fault within this circuit, it will trigger **Diagnostic Trouble Code (DTC) 16**.

---

## Troubleshooting DTC 16

If your vehicle is displaying Code 16, the ECU has determined that the injector circuit is not operating within expected parameters.

### Common Causes
*   **Open Circuit:** A broken wire or loose connection between the ECU and one or more fuel injectors.
*   **Failed Injector:** An injector with an internal electrical short or open coil.
*   **ECU Fault:** A damaged driver or component within the ECU responsible for the injector test circuit.

### Diagnostic Steps
1.  **Check Wiring:** Inspect the injector wiring harness for breaks, corrosion, or shorted wires, particularly at the injector connectors.
2.  **Test Injectors:** Use a multimeter to measure the resistance of each injector to ensure they match factory specifications.
3.  **Inspect ECU:** If wiring and injectors are functional, the fault likely lies within the ECU hardware itself.
