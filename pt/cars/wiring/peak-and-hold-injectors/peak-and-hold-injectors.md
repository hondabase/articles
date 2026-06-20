---
summary: 'Peak and Hold injectors are low-impedance fuel injectors (2–5 ohms) that draw 6–2.4 amperes at 12 volts. They require a resistor box for use with most Honda ECUs.'
tags: [injectors, peak-and-hold, low-impedance, fuel-system, wiring, ecu, obd0, obd1, obd2]
applies_to:
  make: Honda
complexity: beginner
---

# Peak and Hold Injectors

## Overview

Peak and Hold injectors, also known as low-impedance injectors, are characterized by a typical impedance of 2–5 ohms. At 12 volts, this impedance results in a current draw of approximately 6–2.4 amperes.

The high current demand causes these injectors to operate at elevated temperatures. The peak current phase opens the injector sharply and decisively, while a lower hold current phase maintains the injector in the open position.

## Integration with Honda ECUs

To operate Peak and Hold injectors with a Honda ECU, you may need to install a **Resistor Box** in series with the injector circuit.

### Resistor Box Requirements by OBD Standard

| OBD Standard | Resistor Box Status | Notes |
|---|---|---|
| **OBD0** | Built-in | Factory-installed resistor box already present |
| **OBD1** | Not included | External resistor box required |
| **OBD2** | Not included | External resistor box required |

> [!IMPORTANT]
> OBD1 and OBD2 systems require an external resistor box to safely operate Peak and Hold injectors. Failure to install a resistor box may damage the ECU's fuel injector driver circuit.

## See Also

- [Resistor Box Installation](/cars/wiring/resistor-box)
- [OBD0 Systems](/cars/tuning/obd0)
- [OBD1 Wiring](/cars/wiring/obd1)
- [OBD2 Wiring](/cars/wiring/obd2)
