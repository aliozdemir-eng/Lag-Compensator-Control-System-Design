# Ramp Response Analysis

This section analyzes the ramp response of the control system before and after applying the lag compensator.

The main purpose of the lag compensator in this project is to improve the steady-state tracking performance for a unit ramp input.

## 1. Uncompensated System

The open-loop transfer function of the uncompensated system is:

G(s) = 2 / (s(s+2))

Since the system has one pole at the origin, it is a **Type-1 system**.

For a unit ramp input, the steady-state error is determined using the velocity error constant:

K_v = lim_(s→0) sG(s)

Substituting the transfer function:

K_v = lim_(s→0) s × 2 / (s(s+2))

K_v = lim_(s→0) 2 / (s+2)

K_v = 2 / 2 = 1

Therefore, the ramp steady-state error is:

e_ss(ramp) = 1 / K_v = 1

This means the uncompensated system is able to follow the ramp input, but with a relatively large steady-state error.

---

## 2. Lag Compensated System

The selected lag compensator is:

G_c(s) = (s + 0.2) / (s + 0.02)

The compensated open-loop transfer function becomes:

G_open,comp(s) = 2(s + 0.2) / ((s + 0.02)s(s+2))

The new velocity error constant is:

K_v(new) = lim_(s→0) sG_open,comp(s)

Substituting:

K_v(new) = lim_(s→0) s × 2(s + 0.2) / ((s + 0.02)s(s+2))

Canceling s:

K_v(new) = lim_(s→0) 2(s + 0.2) / ((s + 0.02)(s+2))

Evaluating at s = 0:

K_v(new) = 2(0.2) / ((0.02)(2))

K_v(new) = 0.4 / 0.04 = 10

Thus, the ramp steady-state error becomes:

e_ss(ramp) = 1 / 10 = 0.1

So the lag compensator reduces the steady-state error by a factor of 10.

---

## 3. Ramp Response Comparison

| Parameter | Uncompensated System | Lag Compensated System |
|----------|----------------------|------------------------|
| System type | Type-1 | Type-1 |
| Velocity error constant K_v | 1 | 10 |
| Ramp steady-state error | 1 | 0.1 |
| Tracking accuracy | Low | Much improved |

---

## 4. Interpretation

The ramp response analysis clearly shows the main benefit of the lag compensator.

The uncompensated system has:

K_v = 1  
e_ss(ramp) = 1

After compensation:

K_v = 10  
e_ss(ramp) = 0.1

This means the compensated system follows the ramp input much more accurately.

The lag compensator improves the low-frequency gain of the system, which directly improves steady-state tracking performance.

This is the expected and desired effect of lag compensation.

---

## 5. Conclusion

The ramp response analysis verifies that the design objective has been achieved successfully.

Main result:

- Velocity error constant increased from 1 to 10
- Ramp steady-state error reduced from 1 to 0.1
- Tracking performance significantly improved

Therefore, the lag compensator successfully satisfies the steady-state design requirement of the project.
