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
| 3   | 3       | 0011   |
| 4   | 4       | 0100   |
| 5   | 5       | 0101   |
| 6   | 6       | 0110   |
| 7   | 7       | 0111   |
| 8   | 8       | 1000   |
| 9   | 9       | 1001   |
| A   | 10      | 1010   |
| B   | 11      | 1011   |
| C   | 12      | 1100   |
| D   | 13      | 1101   |
| E   | 14      | 1110   |
| F   | 15      | 1111   |


Similarly the weight works as for Binary and Decimals, you multiply by the base powered by whatever index starting from the right.

### Notation
In the [[C Programming Language]] you write hexadecimals with a prefix and suffix. The prefix is **0x**. and the suffix is a **b/B**. That means if we are to write FA1D37 as a hexadecimal in C, we would write *0xFA1D37B* or *0xFA1D37b*.

### Conversion
Conversion from hexadecimals to binary is easy. You replace all hex-numbers in the string with the binary value

> [!NOTE] Hexadecimal to Binary Example
> 2BA -> 0010 1011 1010

Conversion from binary to hexadecimals is similarly also easy. You separate the bit string into groups of 4 starting from the right and convert the 4 bits into hex-numbers

> [!NOTE] Binary to Hexadecimal Example
> 1010111010 -> 10 1011 1010 -> 2BA

### Why
Hexadecimals are more compact that decimals and binary numbers. Simultaneously it is also easy to convert hexadecimals.

## Binary Representation
 In a computer the binary representation is explained by the voltage range. Low voltage at about **0.0V to 0.5V represents a 0**, while a high voltage of about **2.8V to 3.3V represents a 1**. There is a clear separation between the values so there are no mistakes.
 The charge required for the high or low voltage take abit of time before the charge is applied.
 
 ![Binary Representation of a Computer|700](Attachments/BinaryRepresentation.png)

## Notation for byte values

**Byte = 8 bits**
**Binary: 00000000<sub>2</sub> to 11111111<sub>2</sub>**
**Decimal: 0<sub>10</sub> to 255<sub>10</sub>**
**Hexa-decimal: 00<sub>16</sub> to FF<sub>16</sub>**

Bytes are the smallest datatype the processor can find the and read from the memory.

# Memorymodel
## A simple machine-model
The processing unit (CPU) and the memory (RAM) closely work together. The CPU will ask the memory for a specific location that it wants to manipulate or access. In return the CPU can receive data or instructions from the RAM.

### Inside the modules

#### CPU
Inside the CPU we have the current instructions that it is working on.
It houses some calculation-units (addition, subtraction etc.)
And it has a register of local data.

#### RAM
The RAM can house Code (instructions), global data, Heaps and Stacks

## Byte-based memorymodel
We can think of the byte-based memory as **huge array of bytes**. In an array each location has an index, which in memory terms are called an [[Address]]. Each element in the array can house 1 byte. 

### Example of ASCII in a byte-based memory
Each letter in an ASCII string is exactly 1 byte. You therefore allocate each letter after each other in the "byte-array".
An example of this is the ASCII string "Hej med jer!".
We convert each letter into their ASCII value and place them after each other into the memory.


| Bytes | Addr.    |
| ----- | -------- |
|       | 00000000 |
|       | 00000001 |
|       | 00000002 |
|       | 00000003 |
| 72    | 00000004 |
| 101   | 00000005 |
| 106   | 00000006 |
| 32    | 00000007 |
| 109   | 00000008 |
| 101   | 00000009 |
| 106   | 00000010 |
| 32    | 00000011 |
| 106   | 00000012 |
| 101   | 00000013 |
| 114   | 00000014 |
| 33    | 00000015 |



### Operating systems and Memory
In real life scenarios the processing unit allocates virtual addresses in the memory. As an abstraction this can be seen as a very very big byte-array. In reality, there can been more RAM modules and there is a hierarchy of different memorytypes.

The operating systems allocates a private address-space for each process (application). Inside this *private area* the application is free to overwrite data and manipulate, however **it cannot overwrite other private areas**.
The operating system and hardware work together translating the virtual addresses into physical actual addresses on the RAM modules.

## Words
Words are a combination of bits that the computer can work with as a natural unit.

Words are **typeless**.

The datatype is reliant what we express it as (signed/unsigned) int, float, instruction, pointer etc.

The length of a word is typically 8, 16, 32 or 64 bits. (power of 2)

### Word Size in Architecture
When talking about fx. a 64bit architecture (AARCH64 or x86-64), we are talking about the maximum word size the architecture can handle in one operation.

Earlier PC's used 32bit architectures, while modern new PC's use 64bit.

### Organizing words in the memory
The organization of words depend on their bit-size.

#### 32-Bit
Say you have an array of 4 32-Bit words. One as previously mentioned on this page  

#### 64-Bit