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
Synthesized attributes, is when a parent gets its value from its children on the parse tree.
## Inherited Attributes
Inherited attributes, is when a node of the parse tree has its value determined by the parent and/or sibling;''