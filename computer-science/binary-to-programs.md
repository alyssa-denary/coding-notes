1. Binary code on punch cards
2. code written in binary code on punch cards, handed 

1 program at a time in punch cards in binary code

computer program fed to computer and spat out output
-used to take days/weeks

then bottleneck was humans feeding the program, vs the computer itself
–> led to creation of operating systems

OS are just programs that have special permissions to manage other programs
-start in 1950s with powerful computers
-automated the manual task of feeding punch cards
-auto started next batch of cards/next program

Computers got cheaper and more widespread, people started sharing software
Configs started changing, people had different kinds of printers and devices `peripherals`

programmers originally had to know all about each kind of `peripheral`
then OS’ managed this through device drivers - standardized mechanism for that type of peripherals

Then computers were so fast they were waiting for printers, readers, etc. to finish before they could do the next task

multitasking for computers started
-os puts that program to sleep while printer prints
-then gets rescheduled
-but each program needs its own memory
-os manages memory allocation
	– different blocks of memory assigned to each program
	- memory virtualized and abstracted by os, so each program “starts” at 0 and goes as high as allowed
		- os manages that this location is actually 1045, for example.
		  `dynamic memory allocation`
- this is also good because `memory protection.` since each program only has access to its own memory
- virtual and protected memory

- gave several users simultantaous access
- `terminal` is a keyboard and screen that connects to a big computer but doesn’t contain any processing power itself

`time sharing` each user could only operate so much memory/processing power

Multix really complicated, did lots of error handling

OS
-`kernel` -  core functionality: memory management, multitasking, dealing with i/o
-programs & libraries

Unix intentionally left out functionality - error handling for one
	- panic: blue screen of death
	- was more versitile as a result
	- more compilers for different programing languages were developed

MS-DOS - originally most popular OS for home computers 
	-did not have mulititasking
	-would crash often, needed computer to be turned off/on

Now, comp use mac-os, linux, etc. 



