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



# Rule Cloning
Rule cloning is duplicating a certain grammar to bypass the need for inherited attributes. Fx. ![[Pasted image 20230307162401.png]]

The productions have been cloned, even though they are syntactically the same. However the associated Semantic Actions are **not** the same.

# Forcing Semantic Actions
 