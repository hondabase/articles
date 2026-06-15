---
summary: 'An overview of Honda On-Board Diagnostics generations (OBD0, OBD1, OBD2a, OBD2b). Learn their differences, connector layouts, and compatibility.'
tags: [obd, reference, wiring]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [dc2, ef, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: OBD
    url: /pgmfi/wiki/library/obd
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Honda OBD Generations Guide (OBD0, OBD1, OBD2a, OBD2b)

On-Board Diagnostics (OBD) systems were introduced to monitor emissions control systems and notify drivers of electrical or mechanical faults. Honda developed several generations of its Programmed Fuel Injection (PGM-FI) diagnostic systems to comply with clean air mandates. For Honda enthusiasts and mechanics, understanding the differences between these generations is critical when diagnosing faults, executing engine swaps, or socketing ECUs for custom tuning.

---

## 1. Honda OBD0 (1988–1991)

Honda's OBD0 system represents the first generation of electronic fuel injection diagnostics, equipped on vehicles like the 4th-generation Civic (EF), CRX, and 2nd-generation Integra (DA).

### Key Features
- **Sensor Monitoring:** Very basic high/low voltage threshold checks. The ECU cannot detect slow component degradation, only complete sensor failures (such as short circuits or severed wires).
- **Distributor Design:** Early models used vacuum advance distributor mechanisms, transitioning to electronic advance in later years.
- **Oxygen Sensor:** Utilizes either a simple 1-wire unheated oxygen sensor or early 4-wire heated configurations depending on the engine.

### Retrieving Trouble Codes
OBD0 ECUs do not illuminate the dashboard Check Engine Light (CEL) to flash diagnostic codes. Instead:
1. Locate the ECU under the passenger footwell carpet or seat.
2. Turn the ignition switch to the ON position.
3. Look through the viewing window in the ECU metal casing.
4. Count the blinks of the red LED on the circuit board (e.g., 9 flashes indicates a cylinder position sensor fault).

---

## 2. Honda OBD1 (1992–1995)

OBD1 is widely considered the golden era for Honda modification and custom tuning. Equipped on vehicles such as the 5th-generation Civic (EG) and 3rd-generation Integra (DC), these ECUs share standardized motherboard architectures, making them highly versatile for socketing.

### Key Features
- **Rationality Checks:** The ECU program monitors inputs to ensure values are logical (rational) relative to engine conditions, rather than just checking if the circuit is open or closed.
- **4-Wire Heated O2 Sensors:** Standards shifted to heated oxygen sensors to bring the emission loop online faster after cold starts.
- **Service Connector Switch (SCS):** A 2-pin connector used to bypass timing advance controls and flash diagnostic codes.

### Retrieving Trouble Codes
1. Locate the 2-pin SCS connector, typically wrapped in blue tape behind the passenger-side kick panel or glovebox.
2. Jump the two pins together using a paperclip or service wire loop.
3. Turn the ignition switch to the ON position.
4. Count the flashes of the dashboard Check Engine Light (CEL):
   - **Long flashes** (1.0 second) indicate the tens digit.
   - **Short flashes** (0.5 second) indicate the units digit.
   - For example, two long flashes followed by three short flashes indicates Code 23 (Knock Sensor).

---

## 3. Honda OBD2 (1996–2001)

Starting in 1996, the United States EPA mandated the standardized OBD2 protocol. Honda redesigned its engine management systems to incorporate a 16-pin Data Link Connector (DLC) and standardized Diagnostic Trouble Codes (DTCs), such as `P0420` for catalyst efficiency.

### Key Features
- **Catalyst Monitoring:** Features a secondary downstream oxygen sensor located behind the catalytic converter to compare exhaust gas oxygen levels with the primary sensor.
- **Rationality & Functionality Monitors:** Performs continuous runtime diagnostics, including misfire monitoring (detecting crankshaft speed fluctuations) and EVAP purge flow leak testing.
- **Flash Memory:** Transitioned away from socketed EPROMs, restricting traditional chipping methods on factory OBD2 boards.

### Honda OBD2 Sub-Generations
Honda split its OBD2 systems into two distinct wiring and ECU plug configurations:
- **OBD2a (1996–1998):** Used in early 6th-generation Civics (EK), mid-cycle Integra models (DC2), and Accord/Prelude models of this era.
- **OBD2b (1999–2001):** Features a redesigned, more compact ECU plug layout. Used in late-model Civics (including the 1999–2000 EM1 Civic Si), late-model Integras, and late-model Preludes.

> [!NOTE]
> Because OBD2 ECUs cannot be easily socketed or emulator-tuned, enthusiasts performing engine swaps or tuning high-performance setups usually use a **converters harness** to plug an older, socketed OBD1 ECU (like a [P28](/cars/sensors/p28) or [P30](/cars/sensors/p30)) directly into the OBD2 chassis wiring harness.

---

## 4. Terminology Casing & Translation

With the introduction of OBD2 standards, the Society of Automotive Engineers (SAE) J1930 protocol standardized the names of engine control components. Honda modified its traditional terminology to match these standards:

| Legacy Honda Name | SAE Standard Name | Description |
| :--- | :--- | :--- |
| **TW Sensor** (Temperature of Water) | **ECT Sensor** | Engine Coolant Temperature sensor |
| **TA Sensor** (Temperature of Air) | **IAT Sensor** | Intake Air Temperature sensor |
| **EACV** (Electronic Air Control Valve) | **IAC Valve** | Idle Air Control valve |
| **PA Sensor** (Pressure of Air) | **BARO Sensor** | Barometric pressure sensor |
| **TPS** (Throttle Position Sensor) | **TP Sensor** | Throttle Position sensor |
| **ECU** (Electronic Control Unit) | **ECM / PCM** | Engine / Powertrain Control Module |

---

## 5. OBD Conversion Compatibility

When converting a Honda between OBD generations during an engine swap or tuning conversion, keep the following hardware differences in mind:

- **Distributors:** OBD0, OBD1, and OBD2 distributors use different plug shapes and internal sensors. Conversion harnesses or repinned plugs are required when mixing generations.
- **Fuel Injectors:** OBD0 injectors are low-impedance (requiring a resistor box), while OBD1 and OBD2 injectors are high-impedance (saturated, requiring no resistor box).
- **Alternators:** Alternator plugs differ between OBD0 (round plug), OBD1 (round plug), and OBD2 (rectangular plug).
- **Distributor Position Sensors:** Ensure the ECU is configured to match the distributor sensor signals (CYP, CKP, TDC) coming from the engine block. Refer to the [cylinder position sensor guide](/cars/sensors/cylinder-position-sensor) for detailed sensor diagnostics.
