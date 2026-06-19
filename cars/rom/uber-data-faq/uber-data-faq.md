---
summary: 'Archived setup and tuning FAQ for the legacy UberData OBD1 Honda ROM editor.'
tags: [tuning, rom, software, obd1]
applies_to:
  models: [civic, integra]
  chassis: [da, dc2, eg]
complexity: intermediate
---

# UberData Tuning FAQ

UberData is a legacy Honda OBD1 ROM editor. This article preserves its archived setup and tuning FAQ while identifying its example values as historical guidance rather than a ready-to-run calibration.

> [!WARNING]
> The example settings in this archived FAQ are not a safe tune for every engine. Verify ROM compatibility, use suitable instrumentation, and tune under controlled conditions.

## Hardware Requirements

The original FAQ specifies a 1992-1995 OBD1 Honda Civic or Integra ECU and lists these socketing parts:

*   **Resistor:** 1/4 W, 1 kohm
*   **Capacitors:** Two 0.1 uF ceramic disc
*   **Address Latch:** 74HC373
*   **Socket:** 28-pin ROM socket
*   **ROM:** 28-pin EPROM (e.g., 27C256)
*   **Programmer:** Compatible ROM programmer

### Socketing Procedure

1.  Desolder the component holes.
2.  Solder a 28-pin socket into the empty ROM footprint.
3.  Solder in the `74HC373`.
4.  Solder a resistor into `R54` (Note: Not required on USDM P72 GS-R ECUs).
5.  Solder 0.1 uF capacitors into `C51` and `C52`.
6.  Install the `J1` jumper.
7.  Insert the ROM in the correct orientation.

> [!CAUTION]
> Installing an EPROM or EEPROM backward can overheat and damage it when power is applied. If a new error appears after socketing, test a verified stock bin and inspect the soldering. Cutting `J1` returns the ECU to stock code.

For a broader hardware guide, see [Introduction to ECU chipping](/cars/rom/introduction-to-ecu-chipping).

## Baseline Bin Suggestions

| Engine | Suggested Baseline |
| :--- | :--- |
| B18A/B18B | `Stock LS/Int274.bin` |
| B18C (incl. Type R) | `Stock GSR/Int273.bin` |
| Non-VTEC D-Series | `P06-Erm Baseline.bin` |
| VTEC D-Series | `P28-Erm Baseline.bin` |

> [!IMPORTANT]
> These are legacy UberData examples. Confirm that a baseline matches the ECU code base, hardware, injectors, sensors, and engine before using it.

## Map Definitions

The archived FAQ describes the UberData grid as follows:

*   **Y-axis:** Engine speed in RPM.
*   **X-axis:** MAP-derived engine load.
*   **Vacuum:** Displayed in inches of mercury (inHg).
*   **Boost:** Displayed in psi.
*   **Fuel Map:** Higher values command more fuel.
*   **Ignition Map:** Values represent degrees before top dead center (BTDC).

> [!NOTE]
> The statement that injectors max out at a fuel value of `800` is software-specific and does not establish actual injector duty cycle.

## Boost Column Configuration

Stock ROMs do not automatically populate the boost side of fuel and ignition maps. The FAQ suggests these calculator examples:

*   **Boost Average Efficiency:** Set to `120%` to generate fuel values.
*   **Boost Ignition Retard:** Set to `1.0` degree per psi to generate ignition values.

> [!WARNING]
> These are archived software examples, not universal safe settings. Required fuel and ignition values depend on the engine, fuel, compression ratio, intake temperature, boost, and other conditions.

## Rev Limits and VTEC

1.  Open the **Rev Limits** tab.
2.  Set **Fuel Cut** to the desired rev limit.
3.  Set **Fuel Resume** approximately 100 RPM lower.
4.  Set the VTEC enable and disable RPM values.
5.  Apply the changes.

## Full Throttle Launch

Full Throttle Launch uses a lower rev limit below a configured vehicle speed.
*   **Fuel Cut:** The launch RPM.
*   **Disable MPH:** The speed at which the launch limiter deactivates.

## Idle Adjustment

Idle speed limits are adjusted under the **Misc** tab. For IACV frequency issues:
*   **Low-idle:** Move the frequency setting left.
*   **High-idle:** Move the frequency setting right.

## TPS Enrichment

TPS enrichment adds extra fuel during rapid throttle opening. The FAQ suggests this scaling for injectors larger than the stock 240 cc/min:

`starting_percent = (240 / new_injector_size) * 100`

Add 5% to 10% to the result (e.g., ~65% for 450 cc/min injectors).

> [!NOTE]
> This rough example does not account for injector dead time, fuel pressure, voltage compensation, or nonlinear low-pulse behavior.

## Fuel Map Scaling

To scale a fuel map for larger injectors, select the entire map and apply a multiplier:

`multiplier_percent = (240 / new_injector_size) * 100`

Add 5% to 10% to the result to account for non-proportional behavior at low pulse widths. Verify all results with measured wideband data.

## Related
- [Introduction to Honda ECU tuning](/cars/fueling/ecu-tuning)
- [Understanding fuel and ignition maps](/cars/fueling/understanding-maps)
- [Injector sizing](/cars/fueling/injector-sizing)
