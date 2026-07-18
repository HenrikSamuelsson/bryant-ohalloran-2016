# CS:AAP Practice Problem 1.2

## Problem

Given the requirement that a 4× performance improvement shall be meet and that our analysis shows that we can only improve 90% of the system. Then how much must we improve the part of the system that is under our control?

## Solution

This is an application of Almdahl's law that can be written as

```text
T_new = (1 − α) × T_old + (α × T_old) / k
```

Given the `4x` performance increase it is suitable to set `T_old` as `1` and `T_new` as `4` in order to simplify the expression to

```text
4 = (1 − α) + α / k
```

Then given that `α` is `0.9` in our system it follows that

```text
4 = 0.1 + 0.9 / k
40 = 1 + 9 / k
39 = 9 / k
k = 9 / 39 
```