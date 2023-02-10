# What are Tombstone Diagrams
Tombstone diagrams are used to illustrate the connection between program, compiler and the machines to run the program.
Below can be seen the different tombstone "versions" and their meaning.
![[Pasted image 20230210093342.png]]

# Use
Tombstone diagrams are a way of illustrating the process or lifecycle of a program going from a certain language to another that is executable by the target machine. For example, if you have a program *X*, written in Language *Y*, on a machine that uses language *Z*. You would not be able to run the said program on the machine as the language used by the actual machine, is not the same as what was written for the program. This is where [[Compilers]] come in. A compiler is needed to translate the program from Language *Y* into language *Z*.

# What is a Compiler
A compiler is essentially just a program. The Purpose of a compiler is to translate specific language into another and give that as the output. A Compiler therefore takes an input language and an output language. Fx. a C-compiler for an *x86* machine, would take an input of a *.c* file. and the output would be *x86 machine code*. 

# Cross-compilation
Cross-compilation is used when a program is written in language *X* for a target language *Y* on a machine using language *Z*. By cross-compilation, a compiler is used to compile the language into the language of the target machine rather the language of the same machine. A compiler used for cross compilation therefore uses language *Z* going from language *X* to *Y*. This is illustrated in the picture below:
\
![[Pasted image 20230210092903.png|Illustration of Cross compilation]]

As seen on the illustration, Tetris is here written in the language *C* and the target is an *ARM* machine. And the machine used at development is an *x86* machine. Using cross-compilation then translate the Tetris program from *C* to *ARM* using a compiler build for *x86* machines.

# Two Stage Compilation

Two Step Compilation is quite self-explainatory. A compiler translate a program from language *X* into *Y*, and another compiler translate the output of the first compiler from language *Y* to *Z*. This is used for Java, which translates from Java to JVM to Machine Code. 
It can also be used when writing in different level languages. Fx. going from Java to C to Machine Code (Pretty much all machines have a C-compiler and therefore compiling into C can be beneficial. ![[Pasted image 20230210093523.png]]

## How is Two Stage Compilation beneficial?


# Compiling a Compiler
Compiling a compiler, works as seen below:
![[Pasted image 20230210093730.png]]

In the illustration a compiler for *Java* to *x86* is written in *C*. A *C* to *x86* compiler is then used to translate said compiler into *x86* machine code so it can run on the *x86* host machine. In the end you have compiled a *Java* to *x86* compiler written in *C* into a *Java* to *x86* compiler in *x86*.

# Interpreters (Aka. Abstract (or virtual) machine)
Interpreters work as a translation layer between the language of the program and the machine. In this case the program is never compiled. This makes the program more portable. As the source code can just be send to anyone, and it is up to them to have an interpreter to translate the language for them.

## Intermediate Translation
The downside of using interpreters is that you are essentially giving the source code out publicly to someone else. Through intermediate translation you as the developer can compile the language as close to machine code as possible, while still allowing it to be run through an interpreter. Intermediate Translation is closely related to Two Stage Compilation.


## Interpreter vs Compiler
![[Pasted image 20230210101629.png]]
# Bootstrapping
Bootstrapping is writing a compiler in the same language as the source language that is to be compiled. ![[Pasted image 20230210101956.png]]
![[Pasted image 20230210102211.png]]

As seen on the illustrations, You want to implement a *Java* to *Machine Code* compiler written in *Java*. This is done by using a *Java* to *JVM* compiler, which generates a *Java* to *Machine Code* Compiler for the *JVM* interpreter. So by now it could be used if it is run with a *JVM* interpreter. However to complete compile, we using the *Java* to *Machine Code* compiler for *JVM*, to compile the initial *Java* to *Machine Code* In *Java* into the *Java* to *Machine Code* for *Machine Code*. 


## The satanic way lol
You can write a compiler from a certain language *X* to *Y* in language *Z*. Then use a *Z* to *X* compiler to get a compiler from *X* to *Y* written in *X*.

Using the very same output compiler to compiler it self would yield a new compiler that can be used. See the illustration below for a *JVM* to *M* compiler this way.![[Pasted image 20230210103231.png]]![[Pasted image 20230210103249.png]]
![[Pasted image 20230210103417.png]]


## Compiling a faster compiler using bootstrapping
Compiling a fast compiler can be done using bootstrapping:
![[Pasted image 20230210103643.png]] test