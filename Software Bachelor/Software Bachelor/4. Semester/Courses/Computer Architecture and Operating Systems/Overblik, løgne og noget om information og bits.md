# Use of the C Language

## History
C was developed in the period of 1969-1973 as a [[High-level Programming Language]] for programming on Unix systems by Dennis Ritchie.

It was developed because, back in the day, computers were big and expensive and C was a fast, efficient language being compiled into Assembly

## Use cases
The C programming language is still being used! Mostly for creating Operating Systems, Firmware, Integrated systems and IoT devices. It is highly widespread due to it being available for all processors.

## "High-level Assembly"
C closely related to Assembly, and it is very easy to translate the C language into assembly. You can even easily interface with Assembly in C. C is also highly know due to its pointer allowing to manipulate memory addresses, memory information and bits and bytes.

## The compiler
The C compiler is highly effective meaning it meaning the code size is very compact after compilation and it is very fast.
The translation in the compiler happens as [[Single-pass]] meaning  all symbols need to be declared before use for the compiler to be able to read the solution.

## Standardisation and variations
in 1978 "The C Programming Language" book was released by Dennis Ritchie and Brian Kernighan.
In 1982 the American National Standards for Information Systems (ANSI) established a comitee for the C-standard, which resulted in C89. Later this was ratified in 1990 by ISO (C90).

The C-standard has been revised numerous times since: 1999(C99), 2011(C11), 2018(C18), 202x(C2x)

## "C is quirky, flaws, and a tremendous success"
Programming in C can be very effective, however it is possible to create a functioning solution that is completely unreadable for even professionals. Wrong implementations can give a lot errors and security problems.

Moreover the C programming language is badly specified, meaning that many programming with correct syntax can have undefined problems. C can be rather unpredictable sometimes.


> [!NOTE] C being both a high and low level language
> The C programming language can be seen as both a low-level and high-level programming language. This is due to the nature of the language functions and commands mapping closely to the processor instructions. However C does not abstract to a lot of aspects of modern machines (Multi-level Caching, Parallel instructions, Virtual Memory)


## Other new system-level languages
Some other system-level languages are [D](https://dlang.org/overview.html), [Rust](https://www.rust-lang.org/)

## **Important parts of C for the [[Computer Architecture and Operating Systems]] course**
* Simple data-types and convertion: char, int, long, float, double
* Arrays (1D and 2D), structs.
* Pointers
* Iterative Control Structures (For, While, Do-While, goto)
* Selective Control Structures (if-then-else, conditional statements)
* Expressions and arithmetic: logical conditions and allocation
* Functions with parameters, local and global variables

# Binary and Hex
In general, when calculating numbers we multiply the individual numbers by the base<sup>index</sup> reading from the right side.

## Decimals
Decimal numbers are **base 10**. Decimals are **strings going from 0 to 9**.
Decimals work by going from the right side to the left. You multiple the individual numbers by 10<sup>x</sup>, starting with 0 and working up.
Taking a number like 123<sub>10</sub>, this would give 3\*10<sup>0</sup> + 2\*10<sup>1</sup> + 1\*10<sup>2</sup>.

The number that gives the highest value to the overall number is the first (most left number). Opposite works for the most right having the least value.

## Binary
Binary numbers are **base 2**. Meaning they are a string of numbers **consisting of 0's and 1's**.

Similarly to decimals these are calculated from the right side, however as the Binary numbers are base 2, we multiple by 2<sup>x</sup>.

The weight of the numbers work similarly to decimals with the most left number having the most weight for the value.

## Hexadecimal
Hexadecimals are **base 16**. Because of this, they are quite different to Binary and Decimal numbers. Hexadecimals are **strings from 0-9 and 'A' to 'F'**.

Counting Hexadecimals the values goes as follows:
| Hex | Decimal | Binary |
| --- | ------- | ------ |
| 0   | 0       | 0000   |
| 1   | 1       | 0001   |
| 2   | 2       | 0010   |
| 3   | 3       |        |
| 4   | 4       |        |
| 5   | 5       |        |
| 6   | 6       |        |
| 7   | 7       |        |
| 8   | 8       |        |
| 9   | 9       |        |
| A   | 10      |        |
| B   | 11      |        |
| C   | 12      |        |
| D   | 13      |        |
| E   | 14      |        |
| F   | 15      |        |
