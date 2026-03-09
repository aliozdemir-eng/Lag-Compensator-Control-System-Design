# Component Calculation for Lag Compensator Circuit

The lag compensator designed in the theoretical section has the transfer function

G_c(s) = (s + 0.2) / (s + 0.02)

This transfer function must now be implemented using analog components.

## 1. Standard Lag Compensator Form

The general form of a lag compensator implemented with RC components is

G_c(s) = (1 + sT) / (1 + sβT)

where

T = RC

and

β > 1

The pole and zero locations are

Zero location

s = -1/T

Pole location

s = -1/(βT)

## 2. Matching the Design Parameters

From the designed compensator

G_c(s) = (s + 0.2) / (s + 0.02)

we identify

z = 0.2  
p = 0.02

Thus

T = 1 / z

T = 1 / 0.2

T = 5 seconds

For the pole

βT = 1 / p

βT = 1 / 0.02

βT = 50

Therefore

β = 50 / 5

β = 10

So the lag compensator parameters are

T = 5  
β = 10

## 3. Selecting RC Values

Since

T = RC

we must choose resistor and capacitor values that satisfy

RC = 5

A practical selection is

R = 100 kΩ  
C = 50 µF

because

RC = 100000 × 50×10⁻⁶

RC = 5 seconds

This satisfies the required time constant.

For the pole

βR = 10R

Therefore

R₂ = 1 MΩ

## 4. Final Component Values

The lag compensator can therefore be implemented using

R₁ = 100 kΩ  
R₂ = 1 MΩ  
C = 50 µF

These values generate the required pole and zero locations for the compensator.

## 5. Implementation Summary

Designed compensator

G_c(s) = (s + 0.2) / (s + 0.02)

Implemented with

R₁ = 100 kΩ  
R₂ = 1 MΩ  
C = 50 µF

Time constant

T = RC = 5 s

Pole-zero ratio

β = 10

This configuration produces the required lag compensation effect and can be implemented using a standard operational amplifier based RC network.
