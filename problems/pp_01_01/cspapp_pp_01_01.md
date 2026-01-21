# CS:APP Practice Problem 1.1

## Problem

A truck travels a total distance of **2,500 km** at an average speed of
**100 km/h**, resulting in a baseline travel time of **25 hours**.

### Part A

A **1,500 km** portion of the trip can be driven at **150 km/h**, while the
remaining distance is driven at **100 km/h**.

Determine the **overall speedup** for the trip, expressed as a ratio of the
original travel time to the new travel time.

### Part B

Assume the **1,500 km** portion of the trip can be driven at an adjustable
constant speed **v**, while the remaining distance is driven at **100 km/h**.

Determine the required value of **v** to achieve an **overall speedup of 1.67×**.

## Solution

### Solution Part A

Baseline time:

    T_old = 2500 km / 100 km/h = 25 hours

New time:

    Montana portion:
    1500 km / 150 km/h = 10 hours

    Remaining portion:
    1000 km / 100 km/h = 10 hours

    T_new = 10 + 10 = 20 hours

Overall speedup:

    S = T_old / T_new
      = 25 / 20
      = 1.25×

### Solution Part B

Target speedup:

    S = 1.67
    T_new = T_old / S
          = 25 / 1.67
          ≈ 14.97 hours

The non-Montana portion is fixed:

    T_rest = 1000 km / 100 km/h = 10 hours

Allowed time for the Montana portion:

    T_MT = T_new − T_rest
         ≈ 14.97 − 10
         ≈ 4.97 hours

Required Montana speed:

    v = 1500 km / T_MT
      ≈ 1500 / 4.97
      ≈ 302 km/h

Note:
The book often uses 1.67× as a rounded form of 5/3 ≈ 1.6667.
If S = 5/3 is used exactly, then:

    T_new = 15 hours
    T_MT  = 5 hours
    v     = 1500 / 5 = 300 km/h

## Relation to Amdahl's Law

This problem is a direct application of **Amdahl's law**.

Amdahl's law states that the maximum achievable speedup of a system is
limited by the fraction of the system that cannot be improved:

    S = 1 / ((1 − α) + α / k)

where:

- α is the fraction of the total execution time that can be improved
- k is the speedup factor applied to that fraction

In this analogy, the Montana portion of the trip represents the part of the
system that can be accelerated, while the remaining portion of the trip is
fixed.

In Part A, even though the Montana portion is sped up by a factor of 1.5
(from 100 km/h to 150 km/h), the overall speedup is only 1.25× because
40% of the total travel time is unaffected.

In Part B, achieving an overall speedup of 1.67× requires an extremely
large speedup of the improved portion (approximately 300 km/h), which
illustrates Amdahl's key insight:

To significantly improve total performance, a very large fraction of the
system must be accelerated.

## Answer

- Part A: **1.25×**
- Part B: **about 300 km/h** (≈ **302 km/h** if 1.67× is treated as exact)
