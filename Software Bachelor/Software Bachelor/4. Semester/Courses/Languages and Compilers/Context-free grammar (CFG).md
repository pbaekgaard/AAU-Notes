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


# Extended BNF
BNF is less convenient for repetition and optionality. EBNF introduces *+*, *?* and *\**.
- *R+* indicates the occurrence of one or more Rs, to express repetition (sometime R_opt is used).
- *R?* indicates the occurrence of zero or one Rs, to express optionality (sometimes \[R\] is used).
- *R\** indicates the occurrence of zero or more Rs, to express repetition (sometimes {R} is used).

# Properties of grammars
## Left recursion
A non-terminal N is left-recursive if, starting with a sentential form N, we can produce another sentential form starting with N.
- ex: expression -> expression '+' factor | factor

Right-recursion also exists, but is less important.
- ex: expression -> term '+' expression

A non-terminal N is nullable, if starting with a sentential form N, we can product an empty sentential form.
- ex: expression -> $\lambda$


# From tokens to parse tree
## Top-down parser
The Top-down parser produces the parse tree in pre-order by doing a left-scan, Leftmost derivation. Using top-down we construct the sentence from the left side to the right like english etc. This constructs the parse tree from the root (the top), and eventually creates the sentence at the bottom.

## Bottom-up parser
The Bottom-up parser produces the parse tree in post-order by doing a left-scan, Rightmost derivation in reverse.
Bottom-up parsing constructs the sentence from the right side to the left. This creates the parse tree from the bottom. This essentially means we start with a sentence and builds up to the root.


# Ambiguity
A Grammar is ambiguous if and only if it generates a sentential form that has two or more distinct parse trees.

* If we use the parse tree to indicate precedence levels of the operators, we cannot have ambiguity.
* Operator associativity can also be indicated by a grammar
