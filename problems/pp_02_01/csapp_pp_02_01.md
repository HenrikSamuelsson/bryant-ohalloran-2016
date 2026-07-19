# CS:APP Practice Problem 2.1

This document contains a solution to **Practice Problem 2.1** in **Chapter 2** of *Computer Systems: A Programmer's Perspective* (3rd Global Edition).

## Problem

The original problem statement is intentionally omitted to respect the copyright of the authors and publisher.

## Solution

The problem introduces conversions between hexadecimal and binary numbers. These conversions are fundamental to understanding how data is represented throughout the remainder of the book.

When converting between hexadecimal and binary, it is important to remember that each hexadecimal digit corresponds to exactly four binary digits. The mapping is shown in the table below.

The table is useful when first learning these conversions. With practice, however, the mapping becomes familiar enough that the conversions can usually be performed without referring to a table.

| Hexadecimal | Binary |
| :---------: | :----: |
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
| 8 | 1000 |
| 9 | 1001 |
| A | 1010 |
| B | 1011 |
| C | 1100 |
| D | 1101 |
| E | 1110 |
| F | 1111 |

*Table 1. Hexadecimal-to-binary conversion table.*

### Part A

To convert the hexadecimal number `0x25B9D2` to binary, first remember that the leading `0x` is simply an indicator that the number is written in hexadecimal notation. Then convert each hexadecimal digit individually by looking up its corresponding binary representation in the conversion table above.

| Hexadecimal | Binary |
| :---: | :---: |
| 2 | 0010 |
| 5 | 0101 |
| B | 1011 |
| 9 | 1001 |
| D | 1101 |
| 2 | 0010 |

Concatenating the binary values gives

```text
0010 0101 1011 1001 1101 0010
```

Therefore,

```text
0x25B9D2 = 0010 0101 1011 1001 1101 0010
```

### Part B

To convert binary `1010111001001001` to hexadecimal, first split the number into groups of four bits starting from the right.

```text
1010 1110 0100 1001
```

Then replace each four-bit group with the corresponding hexadecimal digit using the Table 1 conversion table above.

| Binary | Hexadecimal |
| :---: | :---: |
| 1010 | A |
| 1110 | E |
| 0100 | 4 |
| 1001 | 9 |

Concatenating the hexadecimal digits gives

```text
0xAE49
```

Therefore,

```text
1010 1110 0100 1001 = 0xAE49
```

## Answer

A. `0x25B9D2 = 0010 0101 1011 1001 1101 0010`  
B. `1010 1110 0100 1001 = 0xAE49`  

## References

Bryant, R. E., & O'Hallaron, D. R. (2016). *Computer systems: A programmer's perspective* (3rd Global ed.). Pearson.
