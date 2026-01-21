# CS:App Practice Problem 1.1

## Problem

A truck travels a total distance of **2,500 km** at an average speed of
**100 km/h**, resulting in a baseline travel time of **25 hours**.

### Part A

A **1,500 km** portion of the trip can be driven at **150 km/h**, while the remaining distance is driven at **100 km/h**.

Determine the **overall speedup** for the trip, expressed as a ratio \( T_\text{old} / T_\text{new} \).

### Part B

Assume the **1,500 km** portion of the trip can be driven at an adjustable constant speed \( v \), while the remaining distance is driven at **100 km/h**.

Determine the required value of \( v \) to achieve an **overall speedup of
1.67×**.

## Solution

### Solution Part A

Baseline time:

- \( T_\text{old} = \frac{2500}{100} = 25 \) hours

New time:

- Montana portion: \( \frac{1500}{150} = 10 \) hours
- Remaining portion: \( \frac{1000}{100} = 10 \) hours
- Total: \( T_\text{new} = 10 + 10 = 20 \) hours

Overall speedup:

- \( S = \frac{T_\text{old}}{T_\text{new}} = \frac{25}{20} = 1.25\times \)

### Solution Part B

Target speedup:

- \( S = 1.67 \Rightarrow T_\text{new} = \frac{T_\text{old}}{S} = \frac{25}{1.67} \approx 14.97 \) hours

The non-Montana portion is fixed:

- \( T_\text{rest} = \frac{1000}{100} = 10 \) hours

So the allowed time for the Montana portion is:

- \( T_\text{MT} = T_\text{new} - T_\text{rest} \approx 14.97 - 10 = 4.97 \) hours

Required Montana speed:

- \( v = \frac{1500}{T_\text{MT}} \approx \frac{1500}{4.97} \approx 302 \) km/h

Note: The book often uses \( 1.67\times \) as a rounded form of \( \frac{5}{3} \approx 1.6667 \).
If you use \( S = \frac{5}{3} \) exactly, then \( T_\text{new} = 15 \) hours, \( T_\text{MT} = 5 \) hours,
and \( v = \frac{1500}{5} = 300 \) km/h.

## Relation to Amdahl's Law

This problem is a direct application of **Amdahl's law**,

S = 1 / ((1 − α) + α / k),

where α is the fraction of time spent in Montana and k is the speedup factor for that portion of the trip.

Only a fraction of the total execution time (the 1,500 km Montana portion of the trip) can be improved,
while the remaining portion of the trip remains unchanged. As a result, the
overall speedup is limited by the unimproved part of the journey.

In Part A, even though the Montana portion is sped up by a factor of 1.5
(from 100 km/h to 150 km/h), the overall speedup is only 1.25× because
40% of the trip time is unaffected. In Part B, achieving a larger overall
speedup (1.67×) requires an unrealistically large speedup of the improved
portion, illustrating Amdahl's key insight: **to significantly improve total
performance, a very large fraction of the system must be accelerated**.

This corresponds to Amdahl’s law:

## Answer

- Part A: **1.25×**
- Part B: **about 300 km/h** (≈ **302 km/h** if you treat 1.67× as exact)
