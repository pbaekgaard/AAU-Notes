Context-free grammar consists of LHS(Left-hand sides) and RHS(Right-hand sides).
They can be though of a recursive equations.

CFG is usually written in the [[BNF]] Notation.


![[Pasted image 20230213135229.png]]

The picture above explains the following:

A Program in the AC language has a sequence of declarations, a sequence of statements and a *$* symbol to indicate the end of the file.

Dcls (declarations) are either one declaration followed by more declarations or the empty string.
Dcl (declaration) are either a float declaration with an identifier or an integer with an identifier.

Statements is a single statement followed by more statements or the empty string.

a statement is an id, assign, value followed by an expression.
A statement can also be a print and an id.

An expression is plus or minus, a value and an expression. Expressions can also be the empty string.

A value is either an identifier, and integer number or a float number.

![[Pasted image 20230213135837.png]]

# Four-tuble
A context-free grammar is a four-tuble:
$G=(N,\sum,P,S)$
![[Pasted image 20230218110210.png]]