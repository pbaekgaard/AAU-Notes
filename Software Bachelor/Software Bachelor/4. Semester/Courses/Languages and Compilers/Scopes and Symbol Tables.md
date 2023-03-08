# Symbol Tables
The symbol table is a chart of all the symbols of a program. When parsing over the program, the symbol table is filled, containing: Symbol Number, Symbol Name and Attributes.



# Constructing a Symbol Table
If a program imports some function, lets say as follows:
```C
import f(float, float, float)
```
The symbol table would add what ever number the symbol is in the symbol table. here is an example symbol table from the book containing the above function:

| Symbol Number | Symbol Name | Attributes                   |
| ------------- | ----------- | ---------------------------- |
| **1**             | **f**           | **void func(float,float,float)** |
| 2             | g           | void func(int)               |
| 3             | w           | int                          |
| 4             | x           | int                          |
| 5             | x           | float                        |
| 6             | z           | float                        |

As can be seen the function *f*, was the first symbol to be added to the symbol table. The compiler finds the function f when importing and determines its return value (here it is void).

A symbol can appear more than once, the second time it appears its called a redeclaration.

Previously we can seen in an AST the use of *Dcl x*, which refers to the x symbol. AST's are decorated with the use of the symbol table instead. Using the example above, *Dcl w* would become *Dcl 3*, indicating the symbol number instead of the symbol name.

## Static Scopes
For static scoping, scope is computed at compile time, based on program text.
Using static scope we we to find out where a variable was declared. You start by looking if it is in the local scope and then work your way out until you are at the global scope. If the variable can be found, then it was never declared.

## Dynamic Scope
Dynamic scope was considered a mistake.

Used by APL, PostScript and Perl

Dynamic scoping refers to the place a function is called.

Ex.
![[Pasted image 20230308134154.png]]

































# Block-Structured Languages and Scopes



# Basic Implementation Techniques



# Advanced Features

