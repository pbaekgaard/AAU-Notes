# Informal definition of the AC Language
A short informal definition of the AC language. AC is short for addition calculator
## Types
Integer
Float

## Keywords
AC has 3 keywords:
*f* declares a floating point.
*i* declares an integer.
*p* prints the value of a variable.

## Variables
23 possible variable names using lowercase roman alphabet, excluding the three reserved keywords (*f, i, p*). Variables must be declared prioer to using them.

## Conversion
In AC, conversion from integer type to float type is accomplished automatically. Conversion in the other direction is not allowed under any circumstances.

## Translation
*dc* (desk calculator) is a stack-based calculator that uses reverse polish notation.
Stack-based languages commonly serve as targets of translation because they lend themselves to compact representation. Examples include the translation of Java into JVM.

# Formal Definition of AC
Informal definitions are generally vague. Formal definitions uses [[Context-free grammar (CFG)]] to specify language syntax and *regular expressions* to specify basic symbols of a language.

## Syntax Specification

![[Pasted image 20230213124858.png]]
The figure about shows the CFG of the AC language.

### Production symbols (Terminals and Nonterminals)
A Terminal is a grammar symbol that cannot be rewritten. For example, the *id*, *assign*, and *$* symbols have no productions in the figure above, that specify how they can be rewritten. On the other hand there are nonterminal symbols like *Val* and *Expr*, as they have been specified for how they can be rewritten. Nonterminals begin with an uppercase letter and terminals begin with lowercase letters.

## Semantics






# Video Notes

## Phases of a compiler

A Compilers objective is to translate a source program into a object code (target program).

All compilers have some major phases (components)
Different compilers may break the phases into smaller phases.
The different phases in the compiler has a One-To-One correspondance between the programming language definition. 
![[Pasted image 20230213132813.png]]
### Syntax Analysis
After the syntax analysis an [[Abstract Syntax tree]]is created.
In the syntax analysis part of the compiler, the grammar of a language is checked. Through the language specification *Regular Expressions* and *Context-Free Grammar* is specified which determines the rules that the Syntax Analysis should check for.

#### Scanner
The scanner reads the code file letter by letter and finds [[Tokens]]. Fx. it will find *f*, *u*, *n* and *c* in a row and know its a function declaration etc. These tokens are then used as inputs in the Parser.
![[Pasted image 20230213195849.png]]

The image above shows the code of an example Scanner. The scanner reads the code and returns a single token if it is applicable, or an error if not. If the scanner gets to the end of file it returns the *$* token.
![[Pasted image 20230213195927.png]]
ScanDigit is used to specify for integer numbers or float numbers. It concatenates the numbers it receives. If it doesn't find a *dot*, tok.type is set as an integer, else its a float. and it will concatenate all numbers after the dot. and finally return the token with its type and value.

#### Parsing
The Parser makes sure the syntactic phrasing is correct.
For AC, the [[Recursive Descent]] technique is used.
The result of parsing is [[Abstract Syntax tree]]

### Contextual Analysis
In the Context Analysis we check for the rules of the Scope and Types. Out of this phases the decorated abstract syntax tree is generated which is a further elaboration of the Abstract Syntax Tree from the Syntax Analysis. These rules are also called [[Static Semantics]].

#### Symbol table
The symbol table is created from the [[Abstract Syntax tree]].

#### Semantic Analysis
In the Semantic Analysis the [[Abstract Syntax tree]] is decorated.

### Code Generation
The output of the code generation is either an executable program or a program in another seperate language that can be further compiled.

In Code Generation, Semantics are further elaborated [[Dynamic Semantics]].




## Sentential Form
Take an example of using the AC language to do the following:
```
f b
i a
a = 5
b = a + 3.2
p b
$
```
The code above declares a *float b*, *int a* and performs addition and then prints.

![[Pasted image 20230213140254.png]]
The figure above explains how a program is expanded through its [[Context-free grammar (CFG)]]. As seen on the right side, *Prog* can be rewritten as *Dcls Stmts $*. On the left side, line two this is exactly what is done. Then *Dcls* are elaborated as *Dcl Dcls*, and *Dcl* as *floatdcl id*. The next *Dcls* is then changed to *Dcl Dcls* again, and the *Dcl* is changed into *intdcl id*. This goes on until line 20 where we see the format of the code above. This is how the compiler checks if the code format is correct. If any deviation happens that doesn't match, there is an error in the code.

## Token Specification
The token specification determines the Tokens for the Terminals.
![[Pasted image 20230213141032.png]]
The *+* sign indicates one or more times. Fx. inum is a number between 0-9 one or more times. So fx 53 is 5 and 3.


## Parse tree vs Syntax tree
The Parse tree shows all the *Dcls*, *Stmt*, *Expr* of a program and actually uses the assignment symbols etc. It is very big and overly complicated compared to the [[Abstract Syntax tree]].

The parse tree looks like the following:

![[Pasted image 20230213143627.png]]

While the [[Abstract Syntax tree]] looks like the following:
![[Pasted image 20230213143653.png]]