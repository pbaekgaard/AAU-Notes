# Signed/Unsigned integers
Integers are normally written as follows:
```C
int x = 13;
int y = -4;
```

When declaring an integer like this, we are essentially declaring a signed integer. The difference between a signed and unsigned integer is that **unsigned integers cannot be negative**.

# Representing negative numbers
There are three ways of representing negative numbers:

## Prefix-bit
Prefix-bit is essentially assigning a bit as an indicator for whether or not it is a negative number.

## Ones' complement
By using Ones' complement we have problems like 0 appearing as both a positive and negative number.

And some standard mathematical rules don't apply like: $a+(-a)\neq 0$

## Two's complement
By using Two's complement we represent negative numbers by the last binary digit being subtracted from the sum. Just like binary, we multiply each 1 and 0 by 2 to the power of the position. Example:
```
10001101 = -115
```

Two further elaborate the example, we take the first number starting from the ri