---
summary: 'Technical specifications of the Honda OBD1 Data Link Connector (DLC) communication protocol, voltage levels, capacitance limits, and serial protocols.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - datalogging
  - software
---

# Data Link Connector (DLC) Communication Protocols

The factory Honda OBD1 Data Link Connector (DLC) is the interface used by diagnostic tools to retrieve diagnostic trouble codes (DTCs) and monitor real-time sensor parameters. The communication physical layer is based on the **ISO 9141** standard (CARB Road Vehicles Diagnostic Systems).

---

## 1. Physical Layer Specifications

The communication line uses battery voltage ($V_{\text{bat}}$, typically 12V–14.4V) as its reference. Logic levels are defined as a percentage of this supply voltage:

### Receiver Voltage Thresholds
*   **Logic "0":** $\le 0.3 \times V_{\text{bat}}$
*   **Logic "1":** $\ge 0.7 \times V_{\text{bat}}$

### Transmitter Voltage Thresholds
*   **Logic "0":** $\le 0.2 \times V_{\text{bat}}$
*   **Logic "1":** $\ge 0.8 \times V_{\text{bat}}$

### Signal Integrity and Capacitance
*   **Transition Time:** A logic bit transition (rise or fall time) must take less than 10% of the total bit duration. This is measured between the 20% and 80% points of $V_{\text{bat}}$.
*   **Line Capacitance Limits:** To prevent signal degradation and pulse rounding over long runs:
    *   Tester and diagnostic cable capacitance ($C_{\text{te}}$): $\le 2\text{ nF}$
    *   On-board wiring capacitance ($C_{\text{obw}}$) + ECU input capacitance ($C_{\text{ecu}}$): $\le 7.6\text{ nF}$
    *   Maximum data line capacitance relative to Ground: $\le 500\text{ pF}$

---

## 2. Data Link Layer (Serial Parameters)

The stock OBD1 ECU communication channel is controlled by the MCU's internal UART.

*   **Baud Rate:** Stock diagnostic tools communicate at **9600 baud** (or 10400 baud on early ISO-compliant systems). 
*   **Configuration:** 8 Data Bits, No Parity, 1 Stop Bit (8N1).
*   **Tuning Bypasses:** Because 9600 baud is too slow for real-time engine tuning and plotting, aftermarket ROM modifications (such as Crome Gold, Hondata, or Neptune) bypass the slow factory K-line routines. They redirect serial datalogging traffic to the **CN2** header port on the ECU board, running at **38400 baud** or **115200 baud** using 5V TTL logic levels.

---

## 3. Application Layer (Protocol Structure)

The communication protocol operates on a master-slave request/response structure. The diagnostic tool (master) must initiate all traffic, and the ECU (slave) responds.

1.  **Handshake / Wakeup:** The tester sends a specific wakeup pattern (slow baud rate sequence) to initialize the line.
2.  **Request Command:** The tester transmits a multi-byte packet containing:
    *   Header / Destination Address
    *   Command Mode (e.g., read RAM register, check DTCs)
    *   Data Address Offset (which sensor value to read)
    *   Checksum Byte (sum of all packet bytes modulo 256)
3.  **ECU Response:** The ECU verifies the checksum and returns the requested data block:
    *   Response Header
    *   Data Payload (e.g., a byte value representing engine coolant temperature scaled in volts)
    *   Checksum Byte
