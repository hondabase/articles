---
summary: 'Guide for repurposing a cruise control switch for Full Throttle Shift (FTS) functionality on EF chassis Honda vehicles.'
tags: [wiring, tuning, fts, cruise-control]
applies_to:
  chassis: [ef]
complexity: intermediate
---

# Cruise Control Switch for Full Throttle Shift (FTS)

This guide describes a community-developed method for repurposing the cruise control/clutch switch in an EF chassis to act as a clutch switch for **Full Throttle Shift (FTS)** functionality.

---

## Installation Overview

The goal is to repurpose a brake light or clutch switch to act as a momentary switch for the FTS rev-limit feature.

### Procedure
1.  **Component Sourcing:** Obtain a brake light switch (commonly found in junkyards).
2.  **Removal:** Remove the original clutch stop adjuster.
3.  **Installation:** Install the new switch in its place.
4.  **Wiring:** Wire the switch so that when contacts are closed, the ECU engages the FTS rev-limit; when open, the ECU operates with the regular rev-limit.

> **Safety Warning:** It is recommended to configure the logic so that the FTS limit is active when the switch is closed. In the event of a circuit failure (e.g., broken wire), this approach forces the engine to the safer FTS rev-limit rather than disabling the rev-limiter entirely, which could lead to engine damage.

---

## Technical Considerations
This is a custom modification requiring basic wiring and circuit testing skills. Ensure the switch reliably signals the ECU before attempting aggressive shifting maneuvers.
