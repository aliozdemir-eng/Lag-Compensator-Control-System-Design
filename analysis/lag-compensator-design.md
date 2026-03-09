# Lag Compensator Design

## 1. Compensator Selection

The uncompensated system has the open-loop transfer function:

G(s) = 2 / (s(s+2))

For this system, the velocity error constant is:

K_v = lim_(s→0) sG(s) = 1

Therefore, the steady-state error for a unit ramp input is:

e_ss(ramp) = 1 / K_v = 1

The design target is to reduce the ramp steady-state error to:

e_ss(ramp) ≤ 0.1

This means the new velocity error constant must satisfy:

K_v(new) ≥ 10

Since the uncompensated system already has K_v = 1, the compensator must provide approximately a tenfold improvement in low-frequency gain.

For this reason, a **lag compensator** is selected.

A lag compensator is generally written as:

G_c(s) = (s + z) / (s + p),   where z > p

The ratio z/p determines the low-frequency gain improvement.  
To obtain an improvement of approximately 10:

z / p = 10

## 2. Pole-Zero Selection

A suitable initial choice is:

z = 0.2  
p = 0.02

Thus, the compensator becomes:

G_c(s) = (s + 0.2) / (s + 0.02)

This choice satisfies:

z / p = 0.2 / 0.02 = 10

So the compensator increases the low-frequency gain by a factor of 10.

## 3. Compensated Open-Loop Transfer Function

The compensated open-loop transfer function becomes:

G_c(s)G(s) = ((s + 0.2) / (s + 0.02)) × (2 / (s(s+2)))

Therefore:

G_open,comp(s) = 2(s + 0.2) / ((s + 0.02)s(s+2))

## 4. Velocity Error Constant of the Compensated System

For the compensated system:

K_v(new) = lim_(s→0) sG_open,comp(s)

Substituting the transfer function:

K_v(new) = lim_(s→0) s × 2(s + 0.2) / ((s + 0.02)s(s+2))

Canceling s:

K_v(new) = lim_(s→0) 2(s + 0.2) / ((s + 0.02)(s+2))

Evaluating at s = 0:

K_v(new) = 2(0.2) / ((0.02)(2))  
K_v(new) = 0.4 / 0.04 = 10

Thus, the new ramp steady-state error becomes:

e_ss(ramp) = 1 / 10 = 0.1

So the compensator satisfies the steady-state design requirement.

## 5. Compensated Closed-Loop Transfer Function

For a unity-feedback system, the closed-loop transfer function is:

T_comp(s) = G_open,comp(s) / (1 + G_open,comp(s))

Substituting:

T_comp(s) = [2(s + 0.2) / ((s + 0.02)s(s+2))] / [1 + 2(s + 0.2) / ((s + 0.02)s(s+2))]

Multiplying numerator and denominator by ((s + 0.02)s(s+2)):

T_comp(s) = 2(s + 0.2) / ((s + 0.02)s(s+2) + 2(s + 0.2))

Now expand:

(s + 0.02)s(s+2) = s(s^2 + 2.02s + 0.04)  
= s^3 + 2.02s^2 + 0.04s

Then add:

2(s + 0.2) = 2s + 0.4

So the denominator becomes:

s^3 + 2.02s^2 + 2.04s + 0.4

Hence, the compensated closed-loop transfer function is:

T_comp(s) = 2(s + 0.2) / (s^3 + 2.02s^2 + 2.04s + 0.4)

## 6. Expected Effect of the Lag Compensator

The lag compensator mainly improves the low-frequency behavior of the system.

Expected benefits:
- Higher velocity error constant
- Lower ramp steady-state error
- Better steady-state tracking performance

Expected trade-off:
- Slower transient response
- Longer settling time
- Possible slight change in overshoot

This happens because the lag compensator introduces a pole close to the origin, which tends to slow down the response.

## 7. Design Summary

Selected lag compensator:

G_c(s) = (s + 0.2) / (s + 0.02)

Compensated open-loop transfer function:

G_open,comp(s) = 2(s + 0.2) / ((s + 0.02)s(s+2))

Compensated velocity error constant:

K_v(new) = 10

Compensated ramp steady-state error:

e_ss(ramp) = 0.1

The compensator successfully satisfies the steady-state design requirement and prepares the system for further transient-response analysis in the next stage.
