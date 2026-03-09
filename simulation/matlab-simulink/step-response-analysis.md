# Step Response Comparison (Simulink)

The figure below shows the step response comparison between the uncompensated system and the lag compensated system obtained using MATLAB/Simulink.

![Step Response](step-response-comparison.png)

## Observations

The uncompensated system exhibits a relatively small overshoot and faster settling behavior.

However, after introducing the lag compensator, the system shows:

- Higher overshoot
- Longer settling time
- Slower transient response

These changes occur because the lag compensator introduces an additional pole close to the origin.

## Performance Values

Simulation results indicate approximately:

Uncompensated system:
- Overshoot ≈ 4.32%
- Settling time ≈ 4.22 s

Lag compensated system:
- Overshoot ≈ 20.69%
- Settling time ≈ 11.23 s

These results are consistent with theoretical expectations and confirm the trade-off introduced by lag compensation: improved steady-state accuracy at the expense of slower transient response.
