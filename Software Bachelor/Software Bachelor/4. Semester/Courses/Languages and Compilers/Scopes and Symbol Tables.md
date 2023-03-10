---
link: https://www.notion.so/Scopes-and-Symbol-Tables-f567e5c3308246088699a6aee1b591bc
notionID: f567e5c3-3082-4608-8699-a6aee1b591bc
---
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

Here if the we look at the x at the left side inside the *begin { sub1 ...*, x refers to the declaration inside *main*. BUT if we call *sub1* inside the * begin { sub2...* function, it refers to the x that is declared inside the sub2 procedure. 



## Symbol Table Interface
The Symbol Table Interface, handles the processing of the symbols. See blow:
![[Pasted image 20230308134531.png]]


# Block-Structured Languages and Scopes
Languages that allow nested name scopes are known as block-structured languages. 

The scope defined by the *innermost* context is known as the **current scope**.
Scopes defined by the current scope and its surrounding scopes are known as *open scopes* or *currently active scopes*.

Rules for interpretation of a name in the presence of multiple scopes:
* At any point in the text of a program, the accessible names are those that
are declared in the current scope and in all other open scopes.

* If a name is declared in more than one open scope, then a reference to the
name is resolved to the innermost declaration—the one that most closely
surrounds the reference.

* New declarations can be made only in the current scope.


You can have a symbol table for each scope in a program.
























# Basic Implementation Techniques



# Advanced Features

