---
summary: 'Complete technical reference pinout tables for Honda OBD2A (1996-1998) and OBD2B (1999-2000) Civic, Integra, and Del Sol ECUs.'
tags: [wiring, ecu, pinout, obd2a, obd2b, honda-tuning]
applies_to:
  models: [civic, crx, del-sol, integra]
  chassis: [ej8, ek4, ek9, dc2]
complexity: intermediate
---

# Honda OBD2A and OBD2B ECU Pinout Reference

This reference guide provides detailed pinout charts for Honda OBD2A (1996–1998) and OBD2B (1999–2000) Engine Control Units (ECUs). These schematics are essential for engine swaps, wiring harness conversions, and installing aftermarket engine management or datalogging interfaces.

---

## Connector Layout Overview

Honda OBD2 system plugs are divided into multi-pin gray connectors:
*   **OBD2A (1996–1998):** Consists of connectors **A (31-pin)**, **C (31-pin)**, and **D (16-pin)**. (Connector B is unused on USDM OBD2A ECUs).
*   **OBD2B (1999–2000):** Consists of connectors **A (32-pin)**, **B (25-pin)**, and **C (31-pin)**.

> [!IMPORTANT]
> Always verify wire color codes on your specific chassis harness before applying power or splicing wires, as pin placement can vary slightly between USDM, JDM, and EDM models.

---

## OBD2A ECU Pinout Table (1996–1998)

### Connector A (31-Pin Main Harness)

| Pin | Wire Color | Signal Name | Description |
| :--- | :--- | :--- | :--- |
| A1 | BRN | INJ1 | Injector Cylinder 1 Output |
| A2 | YEL | INJ2 | Injector Cylinder 2 Output |
| A3 | BLU | INJ3 | Injector Cylinder 3 Output |
| A4 | RED | INJ4 | Injector Cylinder 4 Output |
| A6 | BLK/RED | IACV | Idle Air Control Valve Negative |
| A8 | GRN/YEL | VTS | VTEC Solenoid Valve Control |
| A9 | BLK/WHT | IACV- | IACV 3-Wire Signal (3-pin IACV models) |
| A11 | PNK | MIL | Malfunction Indicator Lamp (Check Engine Light) |
| A12 | BLK/RED | FANC | Engine Coolant Fan Relay Output |
| A16 | RED/BLU | PCS | Purge Control Solenoid Valve |
| A23 | BLK | PG1 | Power Ground 1 |
| A24 | BLK | PG2 | Power Ground 2 |
| A25 | YEL/BLK | IGP1 | Ignition Power Source 1 (+12V Switched) |

### Connector C (31-Pin Engine Sensors)

| Pin | Wire Color | Signal Name | Description |
| :--- | :--- | :--- | :--- |
| C1 | YEL/RED | VCC1 | 5V Reference Voltage Output |
| C4 | RED/BLK | TPS | Throttle Position Sensor Signal |
| C6 | RED/YEL | IAT | Intake Air Temperature Sensor |
| C7 | RED/WHT | ECT | Engine Coolant Temperature Sensor |
| C8 | GRN/WHT | SG1 | Sensor Ground 1 |
| C10 | YEL/WHT | VCC2 | 5V Reference Voltage Output (MAP/TPS) |
| C11 | WHT/RED | MAP | Manifold Absolute Pressure Sensor |
| C14 | BLU/GRN | CKP-M | Crankshaft Position Sensor Negative |
| C15 | BLU/YEL | CKP-P | Crankshaft Position Sensor Positive |
| C18 | WHT/BLU | VSS | Vehicle Speed Sensor Output |

---

## OBD2B ECU Pinout Table (1999–2000)

### Connector A (32-Pin Main Harness)

| Pin | Wire Color | Signal Name | Description |
| :--- | :--- | :--- | :--- |
| A1 | BRN | INJ1 | Injector 1 Ground Drive |
| A2 | YEL | INJ2 | Injector 2 Ground Drive |
| A3 | BLU | INJ3 | Injector 3 Ground Drive |
| A4 | RED | INJ4 | Injector 4 Ground Drive |
| A8 | GRN/YEL | VTS | VTEC Solenoid Power Control |
| A10 | BLK/RED | FANC | Radiator Fan Relay Output |
| A12 | BLK/YEL | IACV | Idle Air Control Valve Control |
| A17 | GRN/RED | MIL | Check Engine Light Ground Output |
| A23 | BLK | PG1 | Power Ground Circuit |
| A24 | BLK | PG2 | Power Ground Circuit |

### Connector B (25-Pin Sensor Harness)

| Pin | Wire Color | Signal Name | Description |
| :--- | :--- | :--- | :--- |
| B1 | YEL/RED | VCC1 | 5V Reference Voltage Output |
| B5 | RED/BLK | TPS | Throttle Position Sensor Signal |
| B10 | WHT/RED | MAP | Manifold Absolute Pressure Sensor Input |
| B11 | WHT | O2S | Primary Heated Oxygen Sensor (HO2S) Signal |
| B13 | RED/YEL | IAT | Intake Air Temperature Sensor Input |
| B14 | RED/WHT | ECT | Engine Coolant Temperature Sensor Input |
| B20 | GRN/WHT | SG1 | Sensor Signal Ground |

---

## Converting OBD2A Harness to OBD2B (or Vice Versa)

When swapping engines or ECUs across 1996–1998 and 1999–2000 chassis, conversion jumpers are strongly recommended.

> [!TIP]
> The primary differences between OBD2A and OBD2B involve distributor plug pinouts (8-pin vs 10-pin), IACV wiring (3-wire IACV vs 2-wire IACV), and secondary O2 sensor positioning.
