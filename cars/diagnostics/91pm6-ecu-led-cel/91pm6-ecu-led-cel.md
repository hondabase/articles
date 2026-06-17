---
summary: 'Technical explanation of the diagnostic LED/CEL blink routine inside the 1991 OBD0 PM6 ECU codebase.'
tags: [diagnostics, ecu]
applies_to:
  brand: Honda
  ecus: [PM6]
  obd: [0]
  models: [civic, crx, integra]
  chassis: [ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: '91PM6 ECU LED CEL'
    url: /pgmfi/wiki/library/91pm6-ecu-led-cel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# 1991 PM6 ECU Diagnostic LED (CEL) Blinking Routine

On OBD0 Honda ECUs like the **1991 PM6** (found in the Civic and CRX Si), diagnostic codes are read via a red LED mounted directly on the ECU circuit board. This LED is visible through a small clear window in the metal ECU cover. When a sensor fault occurs, the Check Engine Light (CEL) is triggered, and the ECU flashes the diagnostic LED to indicate the fault code.

## Code Location and Behavior

For developers disassembling or modifying the 1991 PM6 ROM, the LED blinking routine is located at or near offset **`026E`** in the assembly code.

Rather than utilizing a standard CPU delay loop—which would halt the ECU's execution and disrupt critical fuel/ignition timing calculations—the blinking routine is integrated into the **Timer 0 interrupt handler**.

### Key Characteristics:

* **Interrupt Frequency:** The Timer 0 interrupt handler executes at **100 Hz** (100 times per second).

* **Non-Blocking Logic:** The routine maintains counter registers to track the number of elapsed interrupts. By counting these interrupts, the ECU knows exactly how long to hold the LED in the ON or OFF state to produce clean diagnostic blinks without blocking other processes.
