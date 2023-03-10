---
link: https://www.notion.so/Abstract-Syntax-tree-3c80e5fcfa484ff4acb790721be653b9
notionID: 3c80e5fc-fa48-4ff4-acb7-90721be653b9
---
The work performed by a compiler while parsing is generally termed syntax-directed translation. When constructing the derivation, a parser performs a sequence of syntactic actions (fx. shift and reduce).

# Semantic Actions and Values
## Semantic Actions
Operations that execute in concert with productions are called semantic actions, because they usually address compilation concerns beyond the grammar’s syntax that are related to the meaning of a program.

## Semantic Values
When a semantic action is performed for a production, the semantic actions associated with the production, gets access to a set of semantic values related to the production. One for each symbol.

### Bottom Up
For Bottom up, the semantic values for $X_{1}\dots X_{n}$ are available when $A\to x_{1}\dots x_{n}$ is applied, and the semantic actions determine a value for A.

### Top Down
In Top Down, a value for A is available as the production is applied, and the symbols $X_{1}\dots X_{n}$ have values just after the production is applied.



# Synthesized and Inherited Attributes

## Synthesized attributes
Synthesized attributes, is when a parent node gets its value from its children on the parse tree.
![[Pasted image 20230307150612.png]]
![[Pasted image 20230307151449.png]]
![[Pasted image 20230307151521.png]]
In the second picture above (with the red marker). The values are generated starting from the bottom (Bottom Up). The values are are calculated by the semantic action (semantic rule) shown on the last picture. 
## Inherited Attributes
Inherited attributes, is when a node of the parse tree has its value determined by the parent and/or siblings' node.
![[Pasted image 20230307150617.png]]
An example is in terms of type declaration. fx. D -> T L
L inherits its type from T.
[Synthesized and Inherited Attributes in Syntax directed definition(SDD) in compiler design - YouTube](https://youtu.be/Fk9GtuHaCHM?t=972) explains inherited attributes


# Bottom-Up Syntax-Directed Translation
Bottom-up parser operates two stacks:
* The syntactic stack (also called the parse stack) manipulates terminal and nonterminal symbols as described in Chapter 6 
* The semantic stack manipulates semantic values associated with the grammar symbols.



## Rule Cloning
Rule cloning is duplicating a certain grammar to bypass the need for inherited attributes. Fx. ![[Pasted image 20230307162401.png]]

The productions have been cloned, even though they are syntactically the same. However the associated Semantic Actions are **not** the same.

## Forcing Semantic Actions
"Forcing Semantic Actions" is a technique used in compiler design to associate semantic actions with specific grammar rules. In other words, it is a way to define what happens when a certain rule is matched during the parsing phase of the compilation process.

Forcing semantic actions is achieved by adding code to the grammar rules themselves, in order to specify what should be done when a rule is reduced (i.e., when the rule has been matched and is ready to be processed).

The purpose of forcing semantic actions is to enable the compiler to perform actions beyond simple syntax checking. For example, if the compiler is parsing a programming language, it may need to generate code, assign values to variables, or perform other operations that are specific to the language being compiled. By using semantic actions, the compiler can associate these operations with the corresponding grammar rules and ensure that they are executed at the appropriate time.

Overall, forcing semantic actions is a powerful technique that enables compilers to do much more than simply check the syntax of the input program. It allows the compiler to generate code, perform optimizations, and enforce language-specific rules and restrictions, ultimately producing an executable program that behaves correctly according to the language specification.

 - Above came from ChatGPT

## Aggressive Grammar Restructuring
Aggressive Grammar Restructuring is about restructuring the parse tree so that information flows where it is needed for semantic actions. It is recommended to avoid global variables, so creating a parse tree that does not have global variables is recommended (this can be done by processing global variables earlier). Aggressive Grammar Restructuring can also cause subtle changes in the language, which should be carefully checked. A more robust way of doing so, is rewriting the grammar so it can be based on synthesized attributes.

# Top-Down Syntax-Directed Translation
For Top-Down the semantic actions can be written straight into the parser
Inherited values are simply stored as parameters into methods (we pass the values we want to pass down the parse tree into the parse_method).


Synthesized values can be return values of methods.

![[Pasted image 20230307174417.png]]



# Single Pass Compilers
The single pass compiler is based on the fact that it is the parser that drives all the other phases. We splice the contextual analysis and code generation into the code of the parser.
![[Pasted image 20230307175242.png]]
The CODE blocks explain the different contextual analysis and code generation code. CODE can be typechecking, codegeneration etc.

Single Pass was designed for recursive descent parsers.
AC-Parser without action code:
![[Pasted image 20230307175423.png]]

AC-parser with action code (single pass implemented):
![[Pasted image 20230307175505.png]]

# Multi Pass Compilers
A multi pass compiler makes several passes over the program. The output of a phase is then stored and used by the subsequent phase.![[Pasted image 20230307175759.png]]

Java is an example of a multi pass compiled language. Because we can use a variable before its declaration, contrary to C where you have to declare the variable before you can use it.

This indicates that Java is Multi-Pass. It first checks for all declarations before it analyses the declarations use cases.

# Abstract Syntax Trees
AST is like a parse tree with some details omitted.
See [[The AC Language and Compiler]] for more.


