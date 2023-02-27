Generalized nondeterministic finite automaton, are nondeterministic finite automata wherein the transition arrows may have any regular expressions as labels, instead of only members of the alphabet or ℇ.

The GNFA reads blocks of symbols instead of just one symbol like an NFA. 


# Special Form Conditions
* The start state has transition arrows going to every other state but no arrows
coming in from any other state.
* There is only a single accept state, and it has arrows coming in from every
other state but no arrows going to any other state. Furthermore, the accept
state is not the same as the start state.
* Except for the start and accept states, one arrow goes from every state to
every other state and also from each state to itself.