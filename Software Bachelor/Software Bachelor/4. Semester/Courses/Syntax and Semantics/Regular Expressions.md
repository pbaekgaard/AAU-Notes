Regular expressions are expressions build from regular operations.

In Regular Expressions we follow the same rules as for arithmetics:
Parenthesis comes first, then star operation, foloowed by concatentation and finally union.

# Circular Definition
Defining the notion of a regular expression in terms of itself creates a circular definition, which makes the definition invalid.

# Inductive definition
If we define for a language R, were R_1 and R_2 are always smaller than R. we define regular expressions in terms of smaller regular expressions and thereby avoid circularity.

# ∅ and ε are not the same
Ø describes the empty language while the ε describes the empty string. It is critical to know the difference.

R ∪ ∅ = R.
Adding the empty language to any other language will not change it.
R ◦ ε = R.
Joining the empty string to any string will not change it.

R ∪ ε may not equal R.
For example, if R = 0, then L(R) = {0} but L(R ∪ ε) = {0, ε}.
R ◦ ∅ may not equal R.
For example, if R = 0, then L(R) = {0} but L(R ◦ ∅) = ∅.



# Equivalence with Finite Automata
Regular Expressions and finite automata are equivalent in their descriptive power.

Recall [[Finite Automata and Regular Languages]] on how a regular language is one that is recognized by some finite automaton.

Any regular expression can be converted into a finite automaton that recognizes the language it describes.


# Building an NFA from a regular expression
To build an NFA from regular expression you build up from the smallest subexpressions to larger subexpressions until we have an NFA for the original expression.
Remember, Union can be seen as adding something to the language. Fx. (ab U a) gives the following:
{ab} U {a} = {ab, a}

# Converting DFA into equivalent regular expressions

To do this, we need to convert a DFA into a [[Generalized nondeterministic finite automaton]], GNFA. 

## Convert DFA into GNFA
To convert a DFA into GNFA:
* We simply add a new start state with an ℇ arrow to the old start state and a new accept state with ℇ arrows from the old accept states.
* If there are any arrows that have multiple labels, we replace each with a single arrow whose label is the union of the previous labels.
* Finally we add arrows labeled ∅ between states that had no arrows. (A transition labeled with ∅, can never be used.)

## Convert GNFA into Regular Expression
To convert a GNFA into a regular expression we do the following:
* Identify the number of states, (GNFA must have a start and accept state and therefore has atleast k≥2)
* Construct an equivalent GNFA with k-1 states.
* Repeat until k=2.
	* The state between the two states in the last GNFA will be labeled with the equivalent regular expression.

### Creating a GNFA with one fewer state
To do this, we select a state, rip it out of the machine and repair the remainder so that the same language is still recognized. *Any state will do (NOT THE START OF ACCEPT STATE)*.

After removing a state we repair the machine by altering the regular expressions that label each of the remaining arrows. The new labels compensate for the absence of the removed state by adding back the lost computations. The new label going from a state to another is a regular expression that describes all string that would take the machine from the state to the other directly or via the removed state. Example: 