# Hardware Implementation

This section presents the **physical realization** of the Lag Compensator Control System designed throughout the project.

After completing the control system design, simulations, and PCB layout stages, the circuit was implemented using real electronic components in order to experimentally verify the theoretical results.

The hardware development followed a progressive engineering workflow starting from rapid prototyping on a breadboard and ending with a permanent perfboard implementation.

---

## Breadboard Prototype

The first stage of the hardware implementation involved constructing the control circuit on a breadboard.  
This allowed quick validation of the circuit topology and component values before moving to a permanent implementation.

![Breadboard Prototype](breadboard-prototype-test.jpeg)

---

## Early Development Testing

Additional experiments were performed during the development phase in order to observe the system response and verify signal behavior before constructing the final circuit.

![Home Breadboard Testing](home-breadboard-testing.jpeg)

---

## Circuit Construction

Once the circuit behavior was validated, the design was transferred to a **perforated copper board (perfboard)** for permanent implementation.

During this stage the following steps were performed:

- Component placement planning
- Manual soldering of circuit connections
- Power and signal routing
- Hardware debugging and verification

![Circuit Build Process](circuit-build-process.jpeg)

---

## Final Perfboard Circuit

The final circuit implementation contains the analog components required for the lag compensator control system.

Operational amplifiers, resistors, and capacitors were carefully arranged to implement the designed control structure.

![Final Perfboard Circuit](final-perfboard-circuit.jpeg)

---

## Laboratory Testing

After completing the hardware implementation, the circuit was tested in a laboratory environment using professional measurement equipment.

The following instruments were used during testing:

- Function generator
- Oscilloscope
- DC power supply

These devices allowed observation of the system's dynamic response and verification of the circuit operation.

![Initial Laboratory Test](initial-laboratory-test.jpeg)

---

## Final System Comparison

The final experiment compared the behavior of the **uncompensated system** and the **lag compensated system**.

This comparison confirmed that the lag compensator improved the system performance and reduced steady-state error as predicted during the design stage.

![Final System Comparison](final-system-comparison-test.jpeg)

---

## Summary

The hardware implementation successfully demonstrates the transition from theoretical control system design to a fully functional physical circuit.

The experimental results confirm the consistency between:

- theoretical analysis
- simulation results
- practical hardware behavior

This stage validates the effectiveness of the designed lag compensator control system.
