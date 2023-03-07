# Nonregular Languages
Some languages cannot be recognized by any finite automaton.
We can discover this when a machine needs to remember a certain amount of inputs for it to finish at a state, while the certain amount can be unlimited.

# The Pumping Lemma
The *Pumping Lemma* states that all regular languages have a special property. If a language does not have this property, it cannot be regular.

The property states that all strings in a language can be *pumped* if they are at least as long as a certain special value, called the **pumping length**. That means each such string contains a section that can be repeated any number of times with the resulting string remaining in the language.

![[Pasted image 20230305153654.png]]

ö