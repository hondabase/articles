---
summary: 'An Application Programming Interface (API) is a set of functions within a library or DLL that allows software to perform specific tasks through standardized calls.'
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Application Programming Interface (API) Reference

An Application Programming Interface (API) is a defined set of functions, typically contained within a Dynamic Link Library (DLL) or code library, that enables software to execute specific tasks by calling predefined routines.

## Common API Implementations

APIs serve as the bridge between high-level software and low-level system operations. Common examples encountered in automotive tuning and diagnostic software include:

*   **Microsoft Win32 API:** The core set of functions used by Windows applications to interact with the operating system, hardware, and user interface.
*   **X Window System API:** A standard protocol for building graphical user interfaces on Unix-like operating systems.
*   **Crome Script API:** A specialized interface designed for custom scripting within ECU tuning environments, allowing for automated data manipulation and ROM modification.

> [!NOTE]
> APIs abstract the underlying complexity of the system, allowing developers to perform tasks—such as reading ECU memory or writing to a ROM—without needing to manage the low-level hardware communication directly.