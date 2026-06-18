## Resistor Color Code Reference

Use the color bands on through-hole resistors to identify their resistance value before installing ECU jumpers, pull-ups, voltage dividers, or sensor-scaling parts.

### How to Read the Bands

| Resistor Type | Band 1 | Band 2 | Band 3 | Band 4 | Band 5 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **4-band** | 1st digit | 2nd digit | Multiplier | Tolerance | - |
| **5-band** | 1st digit | 2nd digit | 3rd digit | Multiplier | Tolerance |

### Color Values

| Color | Digit | Multiplier | Tolerance |
| :--- | :---: | :--- | :--- |
| Black | 0 | x1 | - |
| Brown | 1 | x10 | +/- 1% |
| Red | 2 | x100 | +/- 2% |
| Orange | 3 | x1,000 | - |
| Yellow | 4 | x10,000 | - |
| Green | 5 | x100,000 | +/- 0.5% |
| Blue | 6 | x1,000,000 | +/- 0.25% |
| Violet | 7 | x10,000,000 | +/- 0.1% |
| Gray | 8 | x100,000,000 | +/- 0.05% |
| White | 9 | x1,000,000,000 | - |
| Gold | - | x0.1 | +/- 5% |
| Silver | - | x0.01 | +/- 10% |
| No band | - | - | +/- 20% |

### Common ECU Examples

| Value | 4-Band Code | Typical Use |
| :--- | :--- | :--- |
| 220 ohm | Red, Red, Brown, Gold | LED/current-limiting or ECU hardware mods |
| 1k ohm | Brown, Black, Red, Gold | Pull-up, jumper, and driver-bias circuits |
| 1.2k ohm | Brown, Red, Red, Gold | Driver-bias circuits such as IACV repair references |
| 4.7k ohm | Yellow, Violet, Red, Gold | Transistor base resistor circuits |
| 10k ohm | Brown, Black, Orange, Gold | Pull-up, pull-down, and sensor-divider circuits |

> [!TIP]
> Always confirm the measured value with a multimeter before soldering. Old ECU resistors can be heat-discolored, and some boards use small surface-mount parts marked with numeric codes instead of color bands.
