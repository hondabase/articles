---
summary: 'Understand which EPROM types are pin-compatible with common Honda OBD0 and OBD1 ECUs and their programming requirements.'
tags: [ecu, eprom, rom, tuning, pinout, reference]
applies_to:
  brand: Honda
complexity: beginner
---

# EPROM Compatibility for Honda OBD0 and OBD1 ECUs

An EPROM (Erasable Programmable Read-Only Memory) is a programmable ROM that can be written using a ROM programmer or burner.

## Pin-Compatible EPROM Types

The **27C256** and **29C256** are the most common EPROM variants that maintain full pin compatibility with Honda OBD0 and OBD1 ECUs.

> [!WARNING]
> The 28C256 is **not** pin-compatible with Honda OBD0 and OBD1 ECUs and cannot be used as a direct replacement.

### 27C256
- **Type:** UV-erasable EPROM
- **Capacity:** 32 KB
- **Compatibility:** OBD0, OBD1
- **Notes:** Requires UV eraser for reprogramming; reusable

### 29C256
- **Type:** Electrically erasable EPROM (EEPROM)
- **Capacity:** 32 KB
- **Compatibility:** OBD0, OBD1
- **Notes:** In-circuit reprogrammable; no external eraser required

## Incompatible Types

| Type | Reason | Status |
|------|--------|--------|
| 28C256 | Pin configuration mismatch | Not compatible |

> [!TIP]
> When selecting an EPROM for your Honda ECU tuning project, verify pin compatibility with your specific OBD revision before purchase.
