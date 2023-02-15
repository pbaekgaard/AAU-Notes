# Alphabets
Generally we use capital Greek letters like $\sum$ and Γ to designate alphabets and a typewriter font for symbols from an alphabet. Example:
$Σ_1$ = {0,1}
$Σ_2$ = {a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z}  
Γ = {0, 1, x, y, z}

## String over an alphabet
String over an alphabet is writing our a string without seperation using an alphabet.
Fx. using the alphabet: $Σ_1$ = {0,1}
01001 is a string over $Σ_1$.

The length of a string over an alphabet is the number of symbols it contains.

$\epsilon$ designates the empty string. The empty string plays the role of 0 in a number system.

The reverse of a string is writing the string is opposite order.

A substring is if a string consecutively appears in another.

efg is a substring of abcdefghijkl.

**Concatenation** is writing a string after another.
Concatenating x and y would be writing x and then y right after without spacing, fx: x = abc, y = def... The concatenation of x and y is then written as xy = abcdef.

**Lexicographic order** is the normal ordering we are familiar with.
**Shortlex** is the same however shorter strings precede longer strings, meaning bcd would come before abcd because abcd is longer.

Say that string x is a prefix of string y if a string z exists where xz = y, and that x is a proper prefix of y if in addition x 6 = y. A language is a set of strings. A 
language is prefix-free if no member is a proper prefix of another member.


# Finite Automata
A Finite Automaton is a machine that has very limited memory and only few states. Fx. a door at a shop has a Finite Automata detecting when to open and close the door.

## Formal Definition of Finite Automaton

In the formal definition we use $\delta$ to depict the transition function. If a finite automaton has an arrow from x to y from input 1, we indicate that by $\delta(x,1)=y$. ![[Pasted image 20230215202519.png]]
### Example of formal definition
![[Pasted image 20230215202714.png]]

Describing a finite automaton by state diagram is not possible in some cases (too big to draw or unspecified parameters).

## Formal Definition of Finite Automaton's Computation
![[Pasted image 20230215203452.png]]

## Regular Language
A language is called a *regular language* if some finite automaton recognizes it.


### Regular language operations
![[Pasted image 20230215203611.png]]

![[Pasted image 20230215203618.png]]

![[Pasted image 20230215203635.png]]
![[Pasted image 20230215203649.png]]