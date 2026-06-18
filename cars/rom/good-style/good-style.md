---
summary: "A guide to maintaining technical clarity and professional standards in Hondabase documentation."
tags: [documentation, style-guide, technical-writing]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Technical Documentation Style Standards

Effective technical documentation relies on plainness, simplicity, orderliness, and sincerity. Style is not an adornment; it is the fundamental structure of the information provided. To ensure high-quality, scannable, and actionable content, all contributors must adhere to the following principles.

## Core Principles

*   **Clarity:** Use direct, professional language. Avoid conversational filler, introductory fluff, and subjective commentary.
*   **Structure:** Organize information logically using headers, bullet points, and tables. Avoid dense, unbroken walls of text.
*   **Objectivity:** Maintain an agnostic tone. Remove references to external community project branding, personal anecdotes, or internal meta-notes.
*   **Precision:** Ensure all technical specifications—such as wire colors, resistor values, and pinout data—are accurate and easy to cross-reference.

## Formatting Requirements

### Scannability
*   Use **bold labels** to highlight critical information or specific component identifiers.
*   Utilize GFM alerts for safety and technical emphasis:
    > [!IMPORTANT]
    > Essential technical details that must be understood before proceeding.

    > [!WARNING]
    > Critical precautions to prevent system failure or data loss.

    > [!CAUTION]
    > Potential for physical damage to hardware or components.

### Technical Components
*   **ECU Wirelists:** Use the `wirelist` component for structured pinout data to ensure searchability.
*   **Image Carousels:** Use carousels for multi-angle views of hardware, ensuring each slide includes descriptive alt text and a caption.
*   **Widgets:** Integrate standard widgets (e.g., `error-codes`, `wideband-wiring-table`) to provide interactive, up-to-date reference data.
*   **Partials:** Reuse common technical blocks, such as the resistor color-code reference, to maintain consistency across the documentation.

## Documentation Maintenance
When editing existing articles, prioritize the removal of outdated conversational notes and ensure the content aligns with current project standards. Focus on creating content that is high-intent and optimized for search engine discovery.
