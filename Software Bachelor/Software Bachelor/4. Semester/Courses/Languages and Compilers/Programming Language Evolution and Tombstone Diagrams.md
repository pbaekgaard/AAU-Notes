# Zuse's Plankalkül
Konrad Zuse built a series of complex and sophisicated computers from electromechanical relays. They were bombed but his Z4 was saved. He moved and worked on a programming language for it alone in a remote Bavarian village.

He wrote the language Plankalkül which translates to *program calculus*. The language was developed in relations to his Ph.D. dissertation. It is dated to 1945 but was published in 1972.

## Remarkably complete
The Plankalkül language was very complete. Its most advanced features are in the area of data structures.
The language's simplest data type is the bit, Integer and floating-point numerics types were built from the bit type.

> *The floating-point type used twos-complement notation and the “hidden bit”
scheme currently used to avoid storing the most significant bit of the normal-
ized fraction part of a floating-point value.*

It also had arrays and records (records are called structs in C-based languages).
Records could include nested records.

It had no explicit *goto* but it inclided iterative statements similar to ADA's *for*, and the *Fin* command which specified an exit out of a given number of iteration loop nestings.

It had *if statements* but not *else*.


# Pseudo-code
Pseudo-code is used in a different sense here. 
## Short Code
Shortcode was developed for the **BINAC** computer, it was later transfered to a **UNIVAC I** it was the primary means of programming those machines. 
![Available operations in Shortcode |700](Attachments/UNIVACOperations.png)


## Speedcoding
Speedcoding was developed by John Backus for the **IBM 701**.
Speedcoding interpreter effectively converted the 701 to a virtual three-address floating-point calculator.

Conditional and unconditional branches and input/output conversions were also part of the virtual architecture.

It included the novel facility to automatically increment address registers. This didn't appear in hardware before the UNIVAC 1107 computers of 1962.


## UNIVAC "Compiling" system
Between 1951 and 1953, a team led by Grace Hopper at UNIVAC developed a series of "Compiling" systems named A-0, A-1 and A-2 that expanded a pseudo-code into machine code subprograms in the same way as macros are expanded into assembly language. 

# IBM 704 and Fortran
## Design
The environment in which the Fortran was developed was as follows: 
1. Computers had small memories and were slow and relatively unreliable.
2. The primary use of computers was for scientific computations.
3. There were no existing efficient and effective ways to program computers.
4. Because of the high cost of computers compared to the cost of programmers, speed of the generated object code was the primary goal of the first Fortran compilers. 
## Fortran I Overview

## Fortran II

## Fortrans IV, 77, 90, 95, 2003, 2008

## Evaluation