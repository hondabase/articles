---
summary: 'Technical logic tables, address line mapping, and boolean gate reductions for building custom Real-Time Programming (RTP) ROM emulation hardware.'
tags: [hardware, tuning]
applies_to:
  models: [integra]
  chassis: {}
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rtp Truth Table'
    url: /pgmfi/wiki/library/rtp-truth-table
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Logic Mapping & Truth Tables for EPROM Emulation (RTP)

Real-Time Programming (RTP) allows tuners to modify fuel and ignition tables in real-time while the engine is running. This is accomplished by replacing the standard read-only EPROM (`27C256`) with a Non-Volatile SRAM (such as the Dallas DS1230AB 32Kx8 NVSRAM). 

Because the NVSRAM supports both read operations (by the ECU) and write operations (from the emulator interface), logic gates must route control signals to prevent data bus conflicts.

---

## 1. Input/Output Signals

A custom RTP board sits between the ECU motherboard socket and the NVSRAM chip. The logic circuits evaluate the following pins:

### Inputs (From ECU Socket / MCU)

* **A15:** Address Line 15 (splits the memory map into lower and upper segments).

* **/WR (/WE):** Write Enable line from the MCU.

* **/OE:** Output Enable (Pin 22 of the standard 27C256 EPROM socket).

* **/CS:** Chip Select (Pin 20 of the standard 27C256 EPROM socket).

### Outputs (To NVSRAM / Motherboard)

* **/IOWE:** Output to the Write Enable lines of other I/O peripherals on the ECU motherboard.

* **/WE:** Write Enable pin on the DS1230 NVSRAM.

* **/OE:** Output Enable pin on the DS1230 NVSRAM.

* **/CE:** Chip Enable pin on the DS1230 NVSRAM.

---

## 2. Complete Logic Truth Table

The following truth table outlines the behavior required to ensure compatibility with both OBD0 and OBD1 motherboards:

| A15 | /WR | /OE | /CS | /IOWE | /WE (NVSRAM) | /OE (NVSRAM) | /CE (NVSRAM) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **0** | $a$ | $b$ | $c$ | $a$ | **1** | $b$ | $c$ |
| **1** | $a$ | $X$ | $X$ | **1** | $a$ | **1** | **0** |

*Here, $a$, $b$, and $c$ represent active signal logic states (high or low), while $X$ represents a "don't care" state.*

---

## 3. Simplified NAND Gate Reduction

Because both OBD0 and OBD1 motherboards handle output enabling (`/OE`) natively as shown above, the Chip Enable (`/CE`) pin on the NVSRAM can simply be tied low (permanently enabled). 

This simplifies the truth table down to address line **A15** and write enable **`/WE`** routing:

| A15 | /WE (Input) | /IOWE (Output) | /WE (NVSRAM Output) | /CE (NVSRAM Output) |
| :---: | :---: | :---: | :---: | :---: |
| **0** | $a$ | $a$ | **1** | **0** |
| **1** | $a$ | **1** | $a$ | **0** |

This simplified logic can be built using a single quad 2-input NAND gate integrated circuit (such as a 74HC00):

$$\text{/IOWE} = \text{/WE} \text{ NAND } \text{!A15}$$

$$\text{/WE}_{\text{NVSRAM}} = \text{/WE} \text{ NAND } \text{A15}$$

$$\text{!/WE} = \text{/WE} \text{ NAND } \text{/WE}$$

$$\text{!A15} = \text{A15} \text{ NAND } \text{A15}$$

### Isolation for Burners

In professional emulation board designs, a diode and transistor are placed on the write-enable lines. This isolates the logic gates when the entire emulator assembly is plugged into a standard EPROM programmer, protecting the logic chips from the high programming voltages (Vpp) applied during initial configuration.
