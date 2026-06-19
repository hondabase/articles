---
summary: 'Technical explanation of address latches (e.g., 74HC373) used in Honda OBD1 ECUs to interface the MCU with external EPROM memory.'
tags: [ecu, hardware, eprom, memory]
applies_to:
  models: [civic, integra, prelude, accord]
  chassis: [ef, eg, ek, da, dc2, bb]
complexity: intermediate
---

# OBD1 ECU Address Latch Reference

In Honda OBD1 ECUs, the microcontroller (MCU) utilizes a multiplexed address/data bus to communicate with external EPROM memory. Because the MCU shares pins for both address and data signals, an address latch is required to demultiplex these signals and maintain a stable memory address while data is being transferred.

## Functionality
The latch acts as a temporary storage buffer for the address lines. When the **ALE** (Address Latch Enable) signal is high, the latch is transparent, allowing the address signals to pass through. When **ALE** transitions to low, the latch "locks" the current state of the address lines, holding them steady for the EPROM to read while the MCU switches the shared bus to data mode.

> [!IMPORTANT]
> The 74HC373 (or equivalent 74HCT373) is the standard octal D-type transparent latch used in OBD1 ECU hardware. Failure of this component will typically result in a "Check Engine Light" (CEL) solid-on condition or a failure to boot the ECU, as the memory cannot be addressed correctly.

## Technical Specifications

| Feature | Specification |
| :--- | :--- |
| **Component Type** | Octal D-Type Transparent Latch |
| **Logic Family** | 74HC / 74HCT |
| **Pin Count** | 20-pin DIP or SOIC |
| **Function** | Address Demultiplexing |

## Troubleshooting and Diagnostics
If you suspect a latch failure, verify the following:

* **Power Supply:** Ensure the VCC pin (Pin 20) is receiving a stable 5V.
* **Ground:** Verify continuity to ground on Pin 10.
* **ALE Signal:** Use an oscilloscope to verify the **ALE** signal (Pin 11) is toggling correctly. If the signal is stuck high or low, the MCU is not signaling the latch to capture the address.
* **Output State:** Check the output pins (Q0–Q7) to ensure they are reflecting the input states (D0–D7) when the latch is enabled.

> [!CAUTION]
> When replacing the latch, use a high-quality desoldering station to avoid damaging the ECU PCB traces. Always use a socket if space permits to facilitate future repairs.

## ECU Component Trace

```wirelist
{
  "title": "74HC373 Latch Pinout Reference",
  "variants": [
    {
      "id": "74hc373",
      "label": "74HC373 Latch",
      "groups": [
        {
          "label": "Control and Data",
          "rows": [
            { "pin": "1", "signal": "OE", "path": "Output Enable (Active Low)", "note": "Connect to GND" },
            { "pin": "11", "signal": "LE", "path": "Latch Enable", "note": "Driven by MCU ALE" },
            { "pin": "20", "signal": "VCC", "path": "5V Power", "note": "Must be stable" }
          ]
        }
      ]
    }
  ]
}
