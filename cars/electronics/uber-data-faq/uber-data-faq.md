---
summary: 'Archived setup and tuning FAQ for the legacy UberData OBD1 Honda ROM editor.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - tuning
  - rom
  - software
sources:
  - name: 'pgmfi.org wiki'
    title: 'Uber Data FAQ'
    url: /pgmfi/wiki/library/uber-data-faq
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# UberData tuning FAQ

UberData is a legacy Honda OBD1 ROM editor. This article preserves its archived setup
and tuning FAQ while identifying its example values as historical guidance rather than
a ready-to-run calibration.

> [!WARNING]
> The example settings in this archived FAQ are not a safe tune for every
> engine. Verify ROM compatibility, use suitable instrumentation, and tune under
> controlled conditions.

## What hardware does the archived guide require?

The original FAQ specifies a 1992-1995 OBD1 Honda Civic or Integra ECU and lists these
socketing parts:

- One 1/4 W, 1 kohm resistor
- Two 0.1 uF ceramic disc capacitors
- One `74HC373` address latch
- One 28-pin ROM socket
- One compatible 28-pin ROM, such as a `27C256`
- A ROM programmer

It gives this socketing sequence:

1. Desolder the component holes.
2. Solder a 28-pin socket into the empty ROM footprint.
3. Solder in the `74HC373`.
4. Solder a resistor into `R54`; the source says this is not needed on a USDM P72 GS-R.
5. Solder 0.1 uF capacitors into `C51` and `C52`.
6. Install the `J1` jumper.
7. Insert the ROM in the correct orientation.

The source notes that `R54` values from 1 kohm through 10 kohm were reported to work and
that 1 kohm was reported to work better with some ROM emulators.

> [!WARNING]
> Installing an EPROM or EEPROM backward can overheat and damage it when
> power is applied. If a new error appears after socketing, test a verified stock bin and
> inspect the soldering. The archived guide says cutting `J1` returns the ECU to stock code.

For a broader hardware guide, see
[Introduction to ECU chipping](/cars/electronics/introduction-to-ecu-chipping).

## Which baseline bin does the archived FAQ suggest?

| Engine described in source | Suggested baseline |
| :--- | :--- |
| B18A/B18B | `Stock LS/Int274.bin` |
| B18C, including Type R | `Stock GSR/Int273.bin` |
| Non-VTEC D-Series | `P06-Erm Baseline.bin` |
| VTEC D-Series | `P28-Erm Baseline.bin` |

These are legacy UberData examples. Confirm that a baseline matches the ECU code base,
hardware, injectors, sensors, and engine before using it.

## What do the map values mean?

The archived FAQ describes the UberData grid this way:

- The Y-axis is engine speed in RPM.
- The X-axis is MAP-derived engine load.
- Vacuum columns are displayed in inches of mercury.
- Boost columns are displayed in psi.
- Higher fuel-map values command more fuel.
- Ignition-map values are degrees before top dead center.

The source also says injectors begin to max out around a displayed fuel value of `800`.
That statement is software-specific and does not by itself establish injector duty cycle.

## How does the archived FAQ populate boost columns?

The source says a stock ROM does not automatically populate the boost side of the fuel
and ignition maps. It gives these UberData calculator examples:

- Set **Boost Average Efficiency** to `120%`, then apply it to generate fuel values.
- Set **Boost Ignition Retard** to `1.0` degree per psi, then apply it to generate
  ignition values.

The FAQ describes Boost Average Efficiency as an estimate of the density change caused
by compressing and heating the intake air. It describes Boost Ignition Retard as the
amount of timing removed per psi.

> [!WARNING]
> These are archived software examples, not universal safe settings.
> Required fuel and ignition values depend on the engine, fuel, compression ratio,
> intake temperature, boost, and other conditions.

## How does the archived FAQ set rev limits and VTEC?

- Open the **Rev Limits** tab.
- Set **Fuel Cut** to the desired rev limit.
- Set **Fuel Resume** about 100 RPM lower.
- Set the VTEC enable and disable RPM values in the same tab.
- Apply the changes.

The correct limits and VTEC crossover must be established for the specific engine and
calibration.

## What is Full Throttle Launch?

The source describes Full Throttle Launch as a lower rev limit used below a configured
vehicle speed. **Fuel Cut** is the launch RPM, and **Disable MPH** is the speed at which
the launch limiter stops applying.

It also mentions retarding timing and adding fuel at the launch RPM to build boost. That
is aggressive legacy tuning guidance and requires careful calibration.

## How does the archived FAQ adjust idle?

The source says to change idle-speed limits under the **Misc** tab. It also describes an
IACV frequency adjustment:

- Move it left for a low-idle problem.
- Move it right for a high-idle problem.

It suggests advancing timing slightly around a raised idle target. Verify the result
against the engine and ECU code rather than applying the advice blindly.

## What is TPS enrichment?

The FAQ describes TPS enrichment as extra fuel added when the throttle opens quickly. It
uses this rough scaling example for injectors larger than the stock 240 cc/min size:

```text
starting_percent = (240 / new_injector_size) * 100
```

The source suggests adding 5% to 10% to the result and gives approximately 65% for
450 cc/min injectors.

> [!NOTE]
> This rough example does not account for injector dead time, fuel pressure,
> voltage compensation, or nonlinear low-pulse behavior.

## What is cold-crank enrichment?

The source describes cold-crank enrichment as fuel added during cold starts. It says
larger injectors can cause rich starts and hesitation, but notes that the UberData
version discussed by the FAQ did not yet support this adjustment.

## How does the archived FAQ scale a fuel map?

The source suggests selecting the entire fuel map and applying this rough multiplier:

```text
multiplier_percent = (240 / new_injector_size) * 100
```

It then suggests adding 5% to 10% because larger injectors do not behave proportionally
at low pulse widths. Treat this only as a historical starting method and verify the
result with measured data.

## Related

- [Introduction to Honda ECU tuning](/cars/electronics/ecu-tuning)
- [Understanding fuel and ignition maps](/cars/electronics/understanding-maps)
- [Injector sizing](/cars/electronics/injector-sizing)
