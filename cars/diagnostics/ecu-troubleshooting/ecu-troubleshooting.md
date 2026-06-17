---
summary: 'A comprehensive troubleshooting guide for diagnosing Honda OBD0 and OBD1 ECU issues, including solid CEL lights, diagnostic trouble codes, and power-up failures.'
tags: [ecu, diagnostics, troubleshooting, obd0, obd1]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: intermediate
---

# Honda OBD0 and OBD1 ECU Troubleshooting

When diagnosing ECU issues, specifically following a modification or chip installation, categorize the symptoms to isolate the failure point.

## Common ECU Failure Symptoms

*   **Blinking CEL:** The Check Engine Light (CEL) displays a pattern of flashes. Refer to the diagnostic tool below to interpret these codes.
*   **Solid CEL:** The CEL remains illuminated continuously. The service check connector fails to trigger code blinks.
*   **No CEL / Poor Operation:** The CEL does not illuminate, but the engine exhibits poor performance or driveability issues.
*   **Idle Issues:** Persistent idle control problems or CEL Code 14. Refer to the [IACV Circuit Fix - R58 & R59](/cars/diagnostics/iacv-circuit-fix-r58-r59) guide.

::: widget error-codes :::

## Troubleshooting Power and Ground (KOEO)

If the vehicle fails to start, verify the ECU is receiving power and ground during the Key On, Engine Off (KOEO) state.

1.  **Verify ECU LED:** Check if the LED on the ECU board is illuminated.
2.  **Sensor Voltage Test:** Measure the voltage at the Throttle Position Sensor (TPS) connector. If you measure +5V, the ECU is receiving power and is properly grounded.
3.  **Main Relay Inspection:** If no voltage is present at the sensors, inspect the Main Relay. 
    *   The Main Relay consists of two internal relays.
    *   Upon ignition, the first relay energizes to supply power to the ECU.
    *   Once the ECU is powered, it grounds the second relay to activate the fuel pump.
    *   **Verification:** You should hear the fuel pump prime for approximately 2 seconds, and the MIL should extinguish after this interval.

> [!IMPORTANT]
> If the fuel pump does not prime and the MIL remains on, the ECU is likely not completing its power-up sequence. Check the Main Relay solder joints and the ECU ground connections at the thermostat housing.

## Troubleshooting Solid CEL

A solid CEL (no blinking) usually indicates that the ECU processor has failed to boot or is stuck in a reset loop.

*   **Check Socketing:** If the ECU was recently chipped, inspect the solder joints on the 28-pin socket. Ensure there are no solder bridges between pins.
*   **Verify ROM:** Ensure the EPROM is seated correctly and the orientation (notch) is correct.
*   **Clock Circuit:** Verify the crystal oscillator is functioning.
*   **Power Supply:** Check the 5V regulator on the ECU board for proper output.