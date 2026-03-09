# Ramp Response Comparison (Simulink)

The figure below shows the ramp response comparison between the uncompensated system and the lag compensated system obtained using MATLAB/Simulink.

![Ramp Response](ramp-response-comparison.png)

## Observations

The uncompensated system follows the ramp input with a noticeable steady-state error.

After introducing the lag compensator, the system tracks the ramp input more accurately.

This is the main design purpose of the lag compensator.

## Performance Interpretation

For the uncompensated system:

- Velocity error constant: K_v = 1
- Ramp steady-state error: e_ss = 1

For the lag compensated system:

- Velocity error constant: K_v = 10
- Ramp steady-state error: e_ss = 0.1

The simulation result confirms that the compensated system reduces the ramp tracking error significantly.

At around t = 20 s, the difference between the compensated response and the reference ramp is approximately 0.1, which matches the theoretical design target.

## Conclusion

The ramp response simulation verifies that the lag compensator improves steady-state tracking performance successfully.

This result confirms the theoretical analysis and demonstrates the effectiveness of the compensator in reducing ramp steady-state error.
