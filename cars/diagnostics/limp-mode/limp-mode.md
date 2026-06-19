---
summary: 'An overview of OBD0 Limp Mode, a fail-safe operating state triggered by major ECU malfunctions that limits engine performance to protect the drivetrain.'
tags: [ecu, diagnostics, obd0, sensors, troubleshooting]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 Limp Mode Diagnostics and Operation

Limp Mode (also known as "Limp Home Mode") is a fail-safe operating state triggered when the ECU detects a critical system malfunction. When active, the Check Engine Light (CEL) remains illuminated solid, indicating that the ECU has bypassed standard ROM-based fuel and ignition mapping.

## Operational Characteristics

In Limp Mode, the ECU relies on a secondary backup processor to maintain engine operation. Because the primary ROM maps are ignored, the engine will exhibit poor performance and limited drivability.

*   **Sensor Input:** The ECU ignores most sensor data, relying exclusively on the TDC (Top Dead Center) sensor and the TPS (Throttle Position Sensor).
*   **Rev Limiter:** A hard rev limiter is enforced at 3,500 RPM to prevent engine damage.
*   **Fuel/Ignition:** The engine runs on fixed, non-optimized backup tables.

> [!WARNING]
> Limp Mode is intended only for short-term operation to reach a service location. Continued operation in this state can lead to poor fuel economy, fouled spark plugs, and potential engine damage due to non-optimized ignition timing.

## Troubleshooting

If the vehicle enters Limp Mode, the ECU has identified a major fault in the engine management system. 

> [!TIP]
> Use the integrated diagnostic tool to identify the specific fault code triggering the Limp Mode state.

::: widget error-codes :::

## Related Technical References

For further information on the backup systems and diagnostic procedures for OBD0 vehicles, refer to the following documentation:

*   [OBD0 Backup System Overview](/cars/diagnostics/obd0backup)
*   [TPS Sensor Calibration](/cars/diagnostics/tps-sensor)
*   [CEL Diagnostic Procedures](/cars/wiring/cel)
