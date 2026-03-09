# Simulink Model Structure

The control system was modeled and analyzed using MATLAB / Simulink.

The model contains two parallel system configurations:

1. Uncompensated control system
2. Lag compensated control system

Both systems receive the same input signals and their outputs are compared using a scope block.

The Simulink model includes:

- Transfer function blocks for the plant
- Transfer function blocks for the lag compensator
- Summation blocks
- Scope block for response visualization

The structure allows direct comparison of system responses for both step and ramp inputs.

This model was used to verify theoretical calculations and analyze transient and steady-state behavior.
