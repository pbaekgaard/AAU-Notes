There are two forms of top-down parsers. [[Context-free grammar (CFG)]], can be used to generate such parsers automatically. (Compiler compilers, or Parser generators).

# Parsing Problem
Parsing problem describes the problem of "reverse engineering" a string of a language, and thereby identifying if a given input string is or is not in a grammar's language.

# Recursive-descent Parser
For the recursive-descent parser we need a procedure for each non-terminal N in the grammar. Fx. If we have a grammar with non terminals: *Sentence*, *Subject*, *Object* etc. We need the procedures: *parseSentence()*, *parseSubject()* and *parseObject()*. 

We also have the method *accept() or expect()*. This method knows what the next expected Terminal Symbol is, and if it doesn't get an expected Terminal, it reports a syntax error.

## Example of parsing methods

If we take the *parseSentence()* method as an example:

We know how the non-terminal *Sentence* is constructed through the grammar of the language. As an example, *Sentence* can be constructed as the following:
*Sentence ::= Subject Verb Object .*

Because we know how the Sentence is to be constructed through the [[Context-free grammar (CFG)]], we can create the parsing function for the non-terminal as such:

```java
private void parseSentence() {
	parseSubject();
	parseVerb();
	parseObject();
	accept('.');
}
```

The parseSentence method here will run all the commands. And if forexample an input is given which doesn't end with a *.*, the *accept()* method will return an error.

The body of parsing methods are just code corresponding to the Right-Hand-Side of the [[Production]] of the [[Context-free grammar (CFG)]].

It becomes abit more complex when we have a production with alternatives fx:
```j
Subject ::= I | a Noun | the Noun
```
The parsing method for Subject would look like the following:
```java
private void parseSubject() {
	if(currentTerminal matches 'I')
		accept('I');
	else if(currentTerminal matches 'a') {
		accept('a');
		parseNoun();
	}
	else if(currentTerminal matches 'the') {
		accept('the');
		parseNoun();
	}
	else
		report syntax error
}
```
Using the above, if we do not see an *I*, *a* or *the*, we know there is an error because a subject needs to start with one of those.
Similarly for Noun:
```j
Noun ::= cat | mat | rat
```
The parsing method for Subject would look like the following:
```java
private void parseSubject() {
	if(currentTerminal matches 'cat')
		accept('cat');
	else if(currentTerminal matches 'mat')
		accept('mat');
	else if(currentTerminal matches 'rat')
		accept('rat');
	else
		report syntax error
}
```

Conversion of an EBNF specification into a Java implementation for a recursive-descent parser is so "mechanical", that it can be automated (JavaCC and Coco/R).

## Recursive Descent Parsing with AST
This is the same as above, however, instead of the parsing methods being void functions, they should return a bit of the [[Abstract Syntax tree]], fx:
```java
private AST parseSentence() {
	AST theAST;
	AST subject = parseSubject();
	AST verb = parseVerb();
	AST object = parseObject();
	accept('.');
	theAST = new Sentence(subject, verb, object);
	return theAST;
}
```
# Table-driven LL Parser