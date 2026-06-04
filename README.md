# Why I created it / what made me come up with it
I had the idea randomly while thinking about other esolangs (like Brainfuck and Befunge). I noticed there’s kind of a gap in most of them—either they’re based heavily on arithmetic or they’re just completely unreadable (like Malbolge). So I decided to go in a different direction. A lot of inspiration came from FPGAs (Field Programmable Gate Arrays). Basically, instead of just running code on a computer, you’re kind of building the computer itself to run the code (at least in a virtual sense). That’s the main idea behind ASS (Assembly Storage System)—you’re not just writing instructions, you’re routing values through logic gates and building computation step by step. I also tried to make it easier than most esolangs (which I did manage), but it’s still a lot harder than normal programming languages like C, C++, or Python. For example: `[|10|>|5|>{</<<&}]` This is just doing a bitwise AND between 10 and 5 (in binary). 

# The tokens and what they mean.
```
[]   Starts and ends the program
#    Marks a valid jump location

-JMP  Jumps if the current value is NOT zero
JMP   Jumps if the current value is zero

{}   Defines an operation block

x    NOT operation (single input)
$    OR operation (two inputs)
&    AND operation (two inputs)

||   Writes current value to tape
<>   Moves pointer / selects tape position / routing for gates

/    Separates inputs for operations

^    Prints current value to screen
```

# Examples of how they work
[|10|>|5|>{</<<&}]
[] starts and ends program
|10| writes 10 to tape
\> moves pointer right
|5| writes 5
\> moves pointer right again
{} starts operation
< selects first input
/ separates second input
<< moves selection two steps left
& performs AND to the selected bytes
} ends operation and stores results on tape
