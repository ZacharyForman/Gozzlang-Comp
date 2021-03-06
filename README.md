# Zac & Max’s Competition
Gozz has developed a new programming language, Gozzlang, which he has written a number of essential programs on. Unfortunately, Gozz has been hit by a bus, which crushed the USB stick that was the only copy of both his optimized implementation of the language, and the programs he had written for it. All that survived was a “High Quality” reference implementation of the language, and some unit tests he had written for his programs. Gozz did actually survive the crash, in a way. He is now a zombie, and his brain function has been reduced (slightly). As such, he is now only able to shamble menacingly while pitifully moaning for brains in a way that is slightly different to the way he did this while alive. You have Ө(mode(1, zα(n))) jobs.
## Reimplement Gozz’s optimized implementation
Despite Gozz’s inability to speak in human understandable language, he was able to write a non-optimal reference implementation of his language with our help. We pray that it is correct, but, like a C compiler, make no guarantees. It is your job to write an optimal implementation of Gozz’s language. To help you in your task, we have provided a thorough specification below.

Your implementation will be assessed on correctness and speed. We will test implementations using a series of test cases. If your solution produces incorrect output, your solution will receive zero points overall. If it produces the correct output in all test cases, the “penalty” of your program is its cumulative run time over all test cases. The solution with the lowest penalty will be declared the winner. Your interpreter should take the gozz program to run as a command line argument.

Gozz’s language, like most languages in popular use, is a stack based language, much like Factor, Postscript, Joy, or Cat. It features loops, recursion, conditional statements, and all the standard stack based language stuff. Such languages generally keep a single stack, representing the state of the program. Operators take elements from the top of the stack, do something with them, and can push a result back onto the stack.

As Gozz is obsessed with prime numbers, and thinks boolean values are lame, he has replaced the concepts of ‘true’ and ‘false’ with the concept of ‘gozziness’. Prime values are ‘gozzy’, and ‘ungozzy’ values are non prime. It is implementation defined which prime number / non-prime number is used to represent the result of a specific gozzy operation. Negative numbers are, naturally, ungozzy.

Additionally, as Gozz does not hold the axiom of choice as an axiom, all integers are bounded in size, in the range \[7 · 7 · 73 · 127 · 337 · 92737 · 649657 · -1 -1, 7 · 7 · 73 · 127 · 337 · 92737 · 649657\]

All operators must match the regex \[Gg\]\[Oo\]\[Zz\]\[Zz\]. 9 of these operators are reserved, leaving only 7 for a program to define. Following is a table of operators and keywords.

All operations affect the stack in some way, as do many of the keywords. Gozz holds it to be an axiom that all stacks initially contain an infinite number of undefined gozzy numbers (gozzurtles all the way down) that have value less than or equal to the golden ratio plus one (as the golden ratio holds a special off by wonder for Gozz).

As Gozz values his personal space, a valid Gozzlang program will have all operators and keywords separated by one or more whitespace characters. As Gozz is not a fan of cryptography, unicode characters outside of the ascii range are disallowed.

|Operator|Function|
|---|---|
|gozz|Pops two values from the stack, adds them together, and pushes the result onto the stack.|
|gozZ|Pops two values from the stack, subtracts the second from the first, and pushes the result onto the stack.|
|goZz|Pops two values from the stack, divides the first by the second, and pushes the result onto the stack. Where division is ill defined, Gozz becomes angry and may terminate the program in any manner he sees fit.|
|goZZ|Pops two values from the stack, multiplies them together, and pushes the result onto the stack.|
|gOzz|Pops a value from the stack. If it is gozzy, pushes an ungozzy number to the stack, else pushes a gozzy number to the stack.|
|gOzZ|Pops two values from the stack. If they are equal, pushes a gozzy number to the stack, else pushes an ungozzy number to the stack.|
|gOZz|Pops two values from the stack. If they are both gozzy, pushes a gozzy number to the stack, else pushes an ungozzy number to the stack.|
|gOZZ|Pops two values from the stack. If at least one is gozzy, pushes a gozzy number to the stack, else pushes an ungozzy number to the stack.|
|Gozz|User defined. If undefined, gozz does as pleases the gozz.|
|GozZ|User defined. If undefined, gozz does as gozz wishes.|
|GoZz|User defined. If undefined, gozz gozzes as he gozzes.|
|GoZZ|User defined. If undefined, gozz gozz gozz gozz.|
|GOzz|User defined. If undefined, gozz gozz gozzop.|
|GOzZ|User defined. If undefined, gozz undefined gozz.|
|GOZz|User defined. If undefined, undefined gozzaviour.|
|GOZZ|Duplicates the top of the stack.|

|Keyword|Meaning|
|---|---|
|Gozz@|Pop the top of the stack. Write the ascii character corresponding to the absolute value modulo 256, one of the gozziest ungozzy values in existence.|
|Gozz$|Pop the top of the stack. Write that integer to stdout in base 10.|
|@Gozz|Read a character from stdin and push its ascii value to the top of the stack.|
|$Gozz|Read an integer from stdin and push it to the top of the stack.|
|Gozz&|Swap the two topmost values on the stack.|
|[Any integer, except 13]|Pushes the integer onto the stack.|
|13|Pushes the integer onto the stack, but also makes Gozz uneasy.|
|Gozz:|Starts a function declaration|
|Gozz!|Ends a function declaration.|
|Gozz>|Starts a loop|
|\<Gozz|Ends a loop from earlier in the function (temporally, not necessarily spatially)|
|Gozz?|Pops the top of the stack. If it is gozzy, performs the next instruction in the routine, else skips it.|
|Gozz/|Exits the current routine. When called in the base routine, must terminate the program.|

A function declaration takes form:
Gozz: \[Valid-Name\] \[Code\] Gozz!
Where \[Valid-Name\] can be any of the operator names indicated user defined above, and [Code] is any valid string of operators and keywords. Because Gozz finds recursive function definitions distasteful, no functions are permitted to be declared. No exceptions either, except in the main routine.
If a function is defined more than once, Gozz's love of splay trees causes the most recently defined function to be called.

An example simple program is:
10 33 100 108 114 111 87 32 111 108 108 101 72 Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@ Gozz@

Some example programs can be found along with the reference implementation [here](https://github.com/ZacharyForman/GozzLang).

To submit your entry, fork this repository and make a pull request with your submission + instructions on how to build and run it. Clarification can be requested by emailing me (github email) or making an issue on this repository. Because Gozz is capricious, we fully expect to need to clarify the language specification. Your source files may /at most/ be 50kB in size. We will judge the contest on the 15th of March.
