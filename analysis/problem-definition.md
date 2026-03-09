# Problem Definition and Design Objective

This project focuses on the analysis and design of a **lag compensator** for a unity-feedback control system in order to improve steady-state performance.

## 1. Uncompensated System

The open-loop transfer function of the uncompensated plant is defined as:

G(s) = 2 / (s(s+2))

For a unity-feedback system, the closed-loop transfer function becomes:

T(s) = G(s) / (1 + G(s))

Substituting the plant transfer function:

T(s) = (2 / (s(s+2))) / (1 + 2 / (s(s+2)))

Multiplying numerator and denominator by s(s+2):

T(s) = 2 / (s(s+2) + 2)

Expanding:

T(s) = 2 / (s^2 + 2s + 2)

## 2. Characteristic Equation

The characteristic equation of the uncompensated system is obtained from the denominator:

s^2 + 2s + 2 = 0

Solving for the poles:

s = [-2 ± sqrt(4 - 8)] / 2  
s = -1 ± j

Therefore, the closed-loop poles are:

s1,2 = -1 ± j

## 3. Dynamic Performance of the Uncompensated System

The standard second-order characteristic equation is:

s^2 + 2ζω_n s + ω_n^2

Comparing with:

s^2 + 2s + 2

we obtain:

2ζω_n = 2  
ω_n^2 = 2

Thus:

ω_n = sqrt(2) = 1.414 rad/s

and

ζ = 2 / (2 × 1.414) = 0.707

### Percent Overshoot

The percent overshoot is calculated by:

M_p = e^((-ζπ)/sqrt(1-ζ^2)) × 100

Substituting ζ = 0.707:

M_p ≈ 4.3%

### Peak Time

Peak time is:

T_p = π / (ω_n sqrt(1-ζ^2))

T_p = π / (1.414 × sqrt(1 - 0.707^2))

T_p = π / (1.414 × 0.707)

T_p ≈ 3.14 s

### Settling Time

Using the 2% criterion:

T_s ≈ 4 / (ζω_n)

T_s = 4 / (0.707 × 1.414)

T_s ≈ 4 s

These results show that the uncompensated system has acceptable transient behavior with low overshoot and moderate settling time.

## 4. Steady-State Error Analysis

Since the open-loop transfer function is:

G(s) = 2 / (s(s+2))

the system contains one pole at the origin, so it is a:

**Type-1 system**

### Step Input

For a Type-1 system, the steady-state error for a unit step input is:

e_ss(step) = 0

### Ramp Input

The velocity error constant is defined as:

K_v = lim_(s→0) sG(s)

Substituting G(s):

K_v = lim_(s→0) s × 2 / (s(s+2))

K_v = lim_(s→0) 2 / (s+2)

K_v = 2 / 2 = 1

For a unit ramp input, the steady-state error is:

e_ss(ramp) = 1 / K_v = 1 / 1 = 1

So the uncompensated system has:

- Step steady-state error = 0
- Ramp steady-state error = 1

## 5. Design Requirement

The main design goal is to reduce the ramp steady-state error.

Required condition:

e_ss(ramp) ≤ 0.1

Since:

e_ss(ramp) = 1 / K_v

the required velocity error constant must satisfy:

1 / K_v ≤ 0.1

Therefore:

K_v ≥ 10

The uncompensated system has:

K_v = 1

So the compensator must increase the velocity error constant by a factor of:

10 / 1 = 10

## 6. Need for a Lag Compensator

A lag compensator is selected because it increases the low-frequency gain of the system, which improves steady-state accuracy.

General form of a lag compensator:

G_c(s) = (s + z) / (s + p),   where z > p

To obtain approximately a tenfold improvement in the velocity error constant, the compensator ratio should satisfy:

z / p ≈ 10

A suitable initial design choice is:

z = 0.2  
p = 0.02

Thus, the compensator becomes:

G_c(s) = (s + 0.2) / (s + 0.02)

This compensator is expected to improve the ramp steady-state error significantly, while introducing only a limited effect on the dominant transient response.

## 7. Summary of the Initial Design Stage

For the uncompensated plant:

- Open-loop transfer function: G(s) = 2 / (s(s+2))
- Closed-loop transfer function: T(s) = 2 / (s^2 + 2s + 2)
- Closed-loop poles: -1 ± j
- Natural frequency: 1.414 rad/s
- Damping ratio: 0.707
- Percent overshoot: approximately 4.3%
- Settling time: approximately 4 s
- Velocity error constant: K_v = 1
- Ramp steady-state error: 1

Design target:

- Increase K_v from 1 to 10
- Reduce ramp steady-state error from 1 to 0.1

For this purpose, a lag compensator structure will be used in the next stage of the project.
