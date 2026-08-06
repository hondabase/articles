---
summary: 'Complete pinout diagram and wiring reference for the Honda PM6 OBD0 ECU found on 1988-1991 Civic Si, CRX Si, and Integra.'
tags: [wiring, ecu, pinout, obd0, pm6, honda-tuning]
applies_to:
  models: [civic, crx, integra]
  chassis: [ef, da]
complexity: intermediate
---

# Honda OBD0 PM6 ECU Pinout Reference

This guide provides the complete ECU pinout for the Honda PM6 Engine Control Unit used in 1988–1991 Civic Si, CRX Si, and OBD0 Integra models (PR4). It covers the three ECU harness connectors: **A (26-pin)**, **B (16-pin)**, and **C (22-pin)**.

---

## PM6 OBD0 Pinout Diagram & Connector Reference

```
Connector A (26-Pin):  [ A1  A3  A5  A7  A9  A11 A13 A15 A17 A19 A21 A23 A25 ]
                      [ A2  A4  A6  A8  A10 A12 A14 A16 A18 A20 A22 A24 A26 ]

Connector B (16-Pin):  [ B1  B3  B5  B7  B9  B11 B13 B15 ]
                      [ B2  B4  B6  B8  B10 B12 B14 B16 ]

Connector C (22-Pin):  [ C1  C3  C5  C7  C9  C11 C13 C15 C17 C19 C21 ]
                      [ C2  C4  C6  C8  C10 C12 C14 C16 C18 C20 C22 ]
```

---

## Connector A (26-Pin Output & Power)

| Pin | Wire Color | Signal | Description |
| :--- | :--- | :--- | :--- |
| A1 | BRN | INJ1 | Fuel Injector #1 Ground Drive |
| A2 | YEL | INJ3 | Fuel Injector #3 Ground Drive |
| A3 | BLU | INJ2 | Fuel Injector #2 Ground Drive |
| A4 | RED | INJ4 | Fuel Injector #4 Ground Drive |
| A11 | BLK/RED | EACV | Electronic Air Control Valve (EACV/IACV) |
| A13 | YEL/BLK | IGP1 | Ignition Switch Power (+12V Switched) |
| A15 | YEL/BLK | IGP2 | Ignition Switch Power (+12V Switched) |
| A16 | BLK | PG1 | Power Ground Circuit |
| A18 | BLK | PG2 | Power Ground Circuit |

---

## Connector B (16-Pin Vehicle Inputs)

| Pin | Wire Color | Signal | Description |
| :--- | :--- | :--- | :--- |
| B1 | RED/WHT | START | Starter Signal Input (+12V during cranking) |
| B2 | BLU/RED | AC | A/C Clutch Switch Input |
| B5 | BLU | ALT | Alternator FR Signal |
| B10 | WHT/BLU | VSS | Vehicle Speed Sensor Input |
| B13 | GRN/YEL | MIL | Check Engine Light Output |
| B16 | WHT/RED | ALTC | Alternator Control Signal |

---

## Connector C (22-Pin Engine Sensors)

| Pin | Wire Color | Signal | Description |
| :--- | :--- | :--- | :--- |
| C1 | YEL/RED | VCC1 | 5V Sensor Power Supply |
| C2 | YEL/WHT | VCC2 | 5V Sensor Power Supply (TPS/MAP) |
| C7 | RED/BLK | TPS | Throttle Position Sensor Signal |
| C11 | WHT/RED | MAP | Manifold Absolute Pressure Signal |
| C12 | RED/YEL | IAT | Intake Air Temperature Sensor |
| C13 | RED/WHT | TW | Engine Coolant Temperature Sensor |
| C14 | GRN/WHT | SG1 | Sensor Ground Circuit |
| C15 | GRN/WHT | SG2 | Sensor Ground Circuit |

> [!NOTE]
> The PM6 ECU uses a dual-point or multi-point injection driver depending on your regional trim. Ensure the resistor box is wired correctly when upgrading to high-impedance or peak-and-hold injectors on OBD0 harnesses.
