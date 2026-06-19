---
summary: 'An overview of wideband oxygen sensor technology, controller options, and integration methods for ECU tuning.'
tags: [sensor, fueling, diagnostics, tuning]
applies_to:
  models: [integra]
  chassis: {}
complexity: intermediate
---

# Wideband Oxygen Sensor Integration and Tuning

A wideband oxygen sensor provides stable output over a much larger range than standard narrowband sensors, making it an essential tool for accurate Air/Fuel Ratio (AFR) monitoring and ECU tuning.

## Wideband vs. Narrowband Sensors

### Narrowband Output
Stock oxygen sensors are narrowband, typically operating in a 0–1V range. They are designed for emissions compliance and only accurately indicate whether the engine is running at, above, or below stoichiometric (14.7:1 AFR). They lack the resolution required for performance tuning.

### Wideband Output
Wideband sensors utilize a more complex element to provide high-resolution data, typically across a 0–5V range. Because these sensors require precise heating and control, they must be paired with a dedicated wideband controller.

## Integration Methods

There are two primary methods for integrating a wideband sensor into your vehicle:

*   **Dedicated Bung:** Install a second bung in the exhaust downpipe for a permanent wideband sensor. This allows the ECU to continue using the stock narrowband sensor for closed-loop operation while the wideband provides data for tuning.
*   **Sensor Replacement:** Replace the stock narrowband sensor with the wideband sensor. The wideband controller is then configured to output a simulated 0–1V narrowband signal to the ECU to maintain factory operation.

> [!IMPORTANT]
> When using a simulated narrowband signal, ensure the controller is properly calibrated to prevent fueling inconsistencies during closed-loop operation.

## Wideband Controller Options

Several manufacturers offer controllers compatible with the Bosch LSU4 sensor series:

*   **Innovate Motorsports:** Features a patent-pending calibration routine and programmable outputs. Includes a datalogging suite.
*   **AEM UEGO:** A robust, standalone controller. Note that its output voltage scaling is unique and may require specific configuration within your tuning software.
*   **PLX Devices:** Offers various controllers with optional integrated LCD displays. Known for high-quality documentation and ease of use.
*   **TechEdge (DIY-WB):** A hobbyist-driven project offering DIY kits, pre-assembled units, or bare circuit boards. Features advanced inputs including RPM and thermocouple logging.

## Bosch LSU4/LSU4.2 Sensor Reference

The Bosch LSU4 series is widely used in OEM applications (Porsche, Audi, VW, Volvo, etc.), making it a cost-effective and reliable choice for aftermarket tuning.

*   **Bosch LSU 4.2:** Part numbers 0 258 007 057 / 058.
*   **Bosch LSU 4:** Part number 0 258 006 066.

## NTK L1H1 Calibration Table

| A/F Ratio | Voltage (V) |
| :--- | :--- |
| 10.01 | 0.000 |
| 10.01 | 0.156 |
| 10.01 | 0.312 |
| 10.01 | 0.468 |
| 10.01 | 0.624 |
| 10.01 | 0.780 |
| 10.29 | 0.936 |
| 10.72 | 1.092 |
| 11.11 | 1.248 |
| 11.42 | 1.404 |
| 11.81 | 1.560 |
| 12.20 | 1.716 |
| 12.59 | 1.872 |
| 13.10 | 2.028 |
| 13.49 | 2.184 |
| 14.12 | 2.340 |
| 14.70 | 2.496 |
| 15.72 | 2.652 |
| 17.01 | 2.808 |
| 18.61 | 2.964 |
| 18.96 | 3.120 |
| 18.96 | 3.432 |
| 18.96 | 3.900 |
| 18.96 | 4.992 |

> [!TIP]
> Always verify the specific voltage-to-AFR scaling provided by your controller's manual, as these values can vary between firmware versions and hardware manufacturers.
