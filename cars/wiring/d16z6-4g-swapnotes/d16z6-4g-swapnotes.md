---
summary: 'Swap guide for installing a D16Z6 engine into an OBD0 (1988–1991) Civic or CRX, covering engine mounts, pulleys, and necessary harness modifications.'
tags: [swap, vtec, wiring, engine-modification, d-series]
applies_to:
  obd: [0, 1]
  models: [civic, crx, del-sol, prelude]
  chassis: [ef, eg, eg-eh, ek]
complexity: advanced
---

# D16Z6 Swap Guide: OBD0 Chassis

This guide outlines the process of swapping a D16Z6 (OBD1 SOHC VTEC) engine into a 4th-generation Civic or 2nd-generation CRX (OBD0 chassis). 

---

## Mechanical Installation

Installing a D16Z6 is very similar to an A6 swap, with minor adjustments required:

*   **Driver's Side Engine Mount:** The A6 mount is wider. You can reuse the A6 mount, though minor grinding of the metal may be required to prevent the timing belt from brushing against it.
*   **Crankshaft Pulley:** Use the D16Z6 pulley, as it is balanced specifically for the Z6 crankshaft.
*   **Manifolds:** Using the Z6 intake and exhaust manifolds is highly recommended for optimal performance. The Z6 intake is ported specifically for the engine's flow characteristics, and the Z6 4-2-1 exhaust manifold outperforms the A6 4-1 manifold.
*   **Clutch/Flywheel:** Use the flywheel and clutch assembly appropriate for the transmission you are using. Note that 88-year models have a different input shaft spline count, requiring specific clutch discs.

---

## Wiring & Electrical Conversion

### Sensor Relocation
*   **MAP Sensor:** On the 93-95 Z6, the MAP sensor is located on the throttle body. You must extend the MAP sensor wiring from the firewall (OBD0 location) to the throttle body (OBD1 location).
*   **Coolant Temperature Sensor:** If using a 93-95 Z6 engine, the sensor is located on the thermostat cover and will require wiring relocation from the back of the block (OBD0 location).

### Distributor Modifications
The Z6 distributor mounts do not align perfectly with the OBD0 head.
*   The top and bottom-right mounting legs will be used.
*   The bottom-left leg will likely require enlargement or cutting to fit correctly.
*   Use large washers to ensure the distributor makes positive, flat contact with the cylinder head.
*   **Note:** Use Z6 spark plug wires and a new distributor O-ring to prevent oil leaks.

### Fuel System
*   **Injectors:** Use the A6 injectors with your stock OBD0 ECU (PM6). 
*   **O-Rings:** Replace all fuel injector O-rings to prevent fire hazards.
*   **DPFI to MPFI:** If your chassis was originally a Dual Point Fuel Injection (DPFI) model, you must convert the car to Multi-Port Fuel Injection (MPFI) before this swap will function.

---

## VTEC Activation
To enable VTEC, you must wire an activation trigger. 
*   **Simple Approach:** Use an RPM-activated switch or adjustable shift light.
*   **Optimal Approach:** Convert to an OBD1 ECU (using a custom harness or ECU conversion) to leverage factory VTEC control logic and optimized fueling maps.
