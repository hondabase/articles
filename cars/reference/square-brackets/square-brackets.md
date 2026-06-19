---
summary: 'Technical guide on the proper use and syntax of square brackets for referencing ECU pins, memory addresses, and hardware components.'
tags: [reference, documentation, syntax]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Square Bracket Syntax and Usage

Square brackets `[]` are used throughout Hondabase technical documentation to denote specific hardware identifiers, memory locations, and ECU pin references. Adhering to these conventions ensures consistency across all technical articles and wirelists.

## Usage Conventions

Square brackets must be used in the following contexts:

*   **ECU Pin References:** Use brackets to isolate pin identifiers when referencing specific connections (e.g., `[A1]`, `[D12]`).
*   **Memory Addresses:** Use brackets to denote hexadecimal memory addresses or offsets within a ROM file (e.g., `[0x8000]`).
*   **Hardware Indices:** Use brackets to identify specific components in a series or array (e.g., `[IC1]`, `[Q101]`).

## Formatting Rules

> [!IMPORTANT]
> Do not use square brackets for general emphasis or as a substitute for parentheses. Their use is strictly reserved for technical identifiers to allow for automated parsing and cross-referencing.

### Examples

| Context | Correct Usage | Incorrect Usage |
| :--- | :--- | :--- |
| **Pinout** | Connect to [A1] | Connect to A1 |
| **Memory** | Located at [0x4000] | Located at 0x4000 |
| **Component** | Check [R12] | Check R12 |

## Troubleshooting Syntax Errors

If a page displays broken formatting or unexpected characters, verify the following:

1.  **Escaping:** If brackets are required as literal text in a code block, ensure they are properly escaped if the rendering engine requires it.
2.  **Nesting:** Avoid nesting brackets (e.g., `[[A1]]`). Use standard parentheses for grouping if necessary.
3.  **Consistency:** Ensure that all references to a specific pin or address use the same bracketed format throughout the entire article to maintain searchability.
