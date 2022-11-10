source: https://www.geeksforgeeks.org/difference-between-compiled-and-interpreted-language/

### What is a compiled language?
A compiled language is a programming language whose implementations are typically compilers and not interpreters. An interpreted language is a programming language whose implementations execute instructions directly and freely, without previously compiling a program into machine-language instructions.

It is one where the program, once compiled, is expressed in the instructions of the target machine; this machine code is undecipherable by humans. Types of compiled language – C, C++, C#, CLEO, COBOL, etc.
![[Screen Shot 2022-11-10 at 11.47.59 AM.png]]

### What is an interpreted language?
An interpreted language is a programming language that is generally interpreted, without compiling a program into machine instructions. It is one where the instructions are not directly executed by the target machine, but instead, read and executed by some other program. Interpreted language ranges – JavaScript, Perl, Python, BASIC, etc.
![[Screen Shot 2022-11-10 at 11.48.48 AM.png]]

![[Screen Shot 2022-11-10 at 11.51.04 AM.png]]
Source: https://www.youtube.com/watch?v=I1f45REi3k4
![[Screen Shot 2022-11-10 at 12.09.45 PM.png]]
1. Compiled
	- Distributed file is in machine code, also known as an executable file since you can take that file and execute it on a machine.
2.  Interpreted
	- Distributed file is the source code
3. Other option is an intermediary of the two that takes the source code 1/2 to machine code, to a language that is adaptable to different machines, and distributes at this step
	- this language known as JIT compilator or just in time code, sometimes also called byte code
	- Distributed file is in Intermediate language/ JIT / Byte code
	- then each machine takes it the rest of the way to machine code
![[Screen Shot 2022-11-10 at 12.16.26 PM.png]]
