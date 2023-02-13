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

### Short about CFG
CFG - Context-free grammar, 

## Semantics

