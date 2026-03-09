# Transient Response Analysis of the Compensated System

After introducing the lag compensator

G_c(s) = (s + 0.2) / (s + 0.02)

the compensated open-loop transfer function becomes

G_open(s) = 2(s + 0.2) / ((s + 0.02)s(s+2))

For a unity feedback system, the closed-loop transfer function is

T(s) = G_open(s) / (1 + G_open(s))

Multiplying numerator and denominator by ((s + 0.02)s(s+2)):

T(s) = 2(s + 0.2) / ((s + 0.02)s(s+2) + 2(s + 0.2))

Expanding the denominator:

(s + 0.02)s(s+2)

= s(s² + 2.02s + 0.04)

= s³ + 2.02s² + 0.04s

Adding the remaining term:

2(s + 0.2)

= 2s + 0.4

Therefore the characteristic equation becomes

s³ + 2.02s² + 2.04s + 0.4 = 0

## Closed-Loop Poles

Solving the characteristic equation numerically gives the closed-loop poles approximately as

s₁,₂ ≈ -0.941 ± j0.942  
s₃ ≈ -0.197

The complex conjugate pair represents the dominant poles of the system.

## Natural Frequency

The natural frequency of the dominant poles can be approximated by

ω_n = √(σ² + ω²)

σ = 0.941  
ω = 0.942

ω_n ≈ √(0.941² + 0.942²)

ω_n ≈ 1.333 rad/s

## Damping Ratio

The damping ratio is calculated by

ζ = σ / ω_n

ζ = 0.941 / 1.333

ζ ≈ 0.706

## Percent Overshoot

Percent overshoot is given by

M_p = e^((-ζπ)/√(1-ζ²)) × 100

Substituting ζ = 0.706

M_p ≈ 4.4 %

## Peak Time

Peak time is

T_p = π / (ω_n √(1-ζ²))

T_p ≈ 3.33 s

## Settling Time

Using the 2% settling-time approximation

T_s ≈ 4 / (ζ ω_n)

T_s ≈ 20 s

## Interpretation

The lag compensator successfully improves steady-state accuracy by increasing the velocity error constant. However, because the compensator introduces a pole close to the origin, the transient response becomes slower.

Main observations:

- Overshoot remains approximately the same
- Settling time increases
- System response becomes slower
- Steady-state tracking accuracy improves

This behavior is expected for lag compensators, which primarily enhance low-frequency gain and steady-state performance rather than transient speed.
