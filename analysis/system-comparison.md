# Comparison of Uncompensated and Lag Compensated Systems

This section compares the main performance characteristics of the original uncompensated system and the lag compensated system.

## 1. Uncompensated System

Open-loop transfer function:

G(s) = 2 / (s(s+2))

Closed-loop transfer function:

T(s) = 2 / (s^2 + 2s + 2)

Closed-loop poles:

s = -1 ± j

Natural frequency:

ω_n = 1.414 rad/s

Damping ratio:

ζ = 0.707

Velocity error constant:

K_v = 1

Ramp steady-state error:

e_ss(ramp) = 1

Percent overshoot:

M_p ≈ 4.3%

Peak time:

T_p ≈ 3.14 s

Settling time:

T_s ≈ 4 s

---

## 2. Lag Compensated System

Selected compensator:

G_c(s) = (s + 0.2) / (s + 0.02)

Compensated open-loop transfer function:

G_open,comp(s) = 2(s + 0.2) / ((s + 0.02)s(s+2))

Compensated closed-loop transfer function:

T_comp(s) = 2(s + 0.2) / (s^3 + 2.02s^2 + 2.04s + 0.4)

Approximate closed-loop poles:

s₁,₂ ≈ -0.941 ± j0.942  
s₃ ≈ -0.197

Natural frequency:

ω_n ≈ 1.333 rad/s

Damping ratio:

ζ ≈ 0.706

Velocity error constant:

K_v = 10

Ramp steady-state error:

e_ss(ramp) = 0.1

Percent overshoot:

M_p ≈ 4.4%

Peak time:

T_p ≈ 3.33 s

Settling time:

T_s ≈ 20 s

---

## 3. Performance Comparison Table

| Parameter | Uncompensated System | Lag Compensated System |
|----------|----------------------|------------------------|
| Open-loop transfer function | 2 / (s(s+2)) | 2(s+0.2) / ((s+0.02)s(s+2)) |
| Closed-loop poles | -1 ± j | -0.941 ± j0.942, -0.197 |
| Natural frequency ω_n | 1.414 rad/s | 1.333 rad/s |
| Damping ratio ζ | 0.707 | 0.706 |
| Percent overshoot M_p | 4.3% | 4.4% |
| Peak time T_p | 3.14 s | 3.33 s |
| Settling time T_s | 4 s | 20 s |
| Velocity error constant K_v | 1 | 10 |
| Ramp steady-state error | 1 | 0.1 |

---

## 4. Discussion

The lag compensator significantly improves the steady-state performance of the system.

The most important improvement is the increase in the velocity error constant from:

K_v = 1 to K_v = 10

As a result, the ramp steady-state error is reduced from:

1 to 0.1

This means the design requirement is successfully satisfied.

On the other hand, the transient response becomes slower.  
The settling time increases considerably because the lag compensator introduces a pole close to the origin.

The overshoot and damping ratio remain nearly unchanged, which shows that the compensator mainly affects the low-frequency behavior of the system rather than drastically changing the dominant oscillatory mode.

## 5. Conclusion

The lag compensator provides a successful trade-off between steady-state accuracy and transient speed.

Main result:

- Steady-state error is greatly reduced
- Low-frequency tracking performance is improved
- Transient response becomes slower
- Design objective is achieved successfully
