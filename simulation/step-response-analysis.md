# Step Response Analysis

This section analyzes the step response of the control system before and after applying the lag compensator.

The goal is to observe how the compensator affects the transient behavior of the system.

## 1. Uncompensated System

Open-loop transfer function:

G(s) = 2 / (s(s+2))

Closed-loop transfer function:

T(s) = 2 / (s² + 2s + 2)

Closed-loop poles:

s = -1 ± j

From these poles we obtain:

Natural frequency:

ω_n = 1.414 rad/s

Damping ratio:

ζ = 0.707

### Step Response Characteristics

Percent overshoot:

M_p ≈ 4.3 %

Peak time:

T_p ≈ 3.14 s

Settling time:

T_s ≈ 4 s

Steady-state error for step input:

e_ss = 0

Because the system is Type-1, the steady-state error for a step input is zero.

---

## 2. Lag Compensated System

Lag compensator:

G_c(s) = (s + 0.2) / (s + 0.02)

Compensated open-loop transfer function:

G_open(s) = 2(s + 0.2) / ((s + 0.02)s(s+2))

Closed-loop characteristic equation:

s³ + 2.02s² + 2.04s + 0.4 = 0

Approximate closed-loop poles:

s₁,₂ ≈ -0.941 ± j0.942  
s₃ ≈ -0.197

The dominant poles are:

-0.941 ± j0.942

### Step Response Characteristics

Natural frequency:

ω_n ≈ 1.333 rad/s

Damping ratio:

ζ ≈ 0.706

Percent overshoot:

M_p ≈ 4.4 %

Peak time:

T_p ≈ 3.33 s

Settling time:

T_s ≈ 20 s

Steady-state error for step input:

e_ss = 0

---

## 3. Step Response Comparison

| Parameter | Uncompensated | Lag Compensated |
|----------|---------------|----------------|
| Percent Overshoot | ≈ 4.3 % | ≈ 4.4 % |
| Peak Time | ≈ 3.14 s | ≈ 3.33 s |
| Settling Time | ≈ 4 s | ≈ 20 s |
| Step Error | 0 | 0 |

---

## 4. Interpretation

The step response shows that the lag compensator does not significantly change the overshoot or damping ratio of the system.

However, it introduces a pole close to the origin, which slows down the system response and increases the settling time.

This behavior is expected because lag compensators mainly improve **steady-state accuracy** rather than transient speed.

The step response confirms that the system remains stable and maintains acceptable transient characteristics after compensation.
