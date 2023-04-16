# Chapter 5: Handling Input and Output

Welcome back, folks. In the previous chapter, we talked about branching and looping instructions. Now, it's time to learn about input and output in ARM assembly programming.

As you might already know, Input and Output (I/O) is an integral part of any computer system. Whether it's a simple calculator or a complex supercomputer, I/O is what makes it possible to interact with the machine.

In this chapter, we'll be discussing the various ways of handling input and output in ARM assembly programming. We'll talk about how to read user input from the keyboard and how to display output on the screen.

But before we jump into the code, let's take a moment to understand why I/O is important in programming.

Think about it like this: Imagine you're a modern-day Robin Hood, sneaking into the local tax collector's office to steal the tax money back and distribute it among the poor. But you can't do it without interacting with the security guard at the front desk. You need to convince him to let you in without raising any alarms.

Similarly, when we write programs, we need to communicate with the computer through I/O operations. Without input and output, our programs would be like Robin Hood without his trusty bow and arrows.

So, get ready to learn about the various instructions and system calls that allow us to interact with the computer's input and output devices.

Let's dive in and become masters of ARM assembly programming!
# The Adventures of Robin Hood: Handling Input and Output

Once upon a time, Robin Hood found himself in a tight spot. He had just stolen from the town’s tax collector -- again -- and was being chased by the Sheriff and his men through the forest. Robin knew he had to find a way to escape, but he needed to communicate with his team of Merry Men and let them know where to meet him.

Luckily, Robin Hood was a skilled programmer, so he quickly pulled out his trusty laptop and started writing a program in ARM assembly language.

```
mov r0, #1   @ get input from keyboard
mov r1, r0
mov r2, #15  @ read up to 15 characters
ldr r7, =4
svc #0
```

With these instructions, Robin was able to read input from the keyboard and store it in memory. But he needed to send this message to his Merry Men.

```
mov r0, #0   @ set to stdout
mov r1, r2
add r2, r2, #1   @ add 1 to size for null terminator
mov r7, #4   @ syscall write
swi #0
```

With these instructions, Robin sent his message to stdout, a file descriptor that represents the standard output of the computer. Now his Merry Men knew where to meet him, and they were able to successfully escape the Sheriff's men.

Thanks to Robin's programming skills and ARM assembly language, he was able to handle input and output with ease.

The End.
# Explanation of the Code

In the Robin Hood story, we saw how Robin used ARM assembly language to handle input and output on his laptop. Let's take a closer look at the code he wrote:

```
mov r0, #1   @ get input from keyboard
mov r1, r0
mov r2, #15  @ read up to 15 characters
ldr r7, =4
svc #0
```

These lines of code use the `mov` instruction to move the value 1 into register `r0`. `r0` is used to specify the source or destination operand for I/O operations. In this case, Robin set `r0` to 1 to indicate that he wanted to read input from the keyboard.

The next line of code uses the `mov` instruction again to copy the value of `r0` into `r1`. This is because the `svc` instruction that Robin will use to perform a system call expects the file descriptor to be stored in `r1`.

The `mov` instruction sets `r2` to 15, indicating that the input buffer should be able to store up to 15 characters.

Finally, Robin uses the `ldr` instruction to load the value of 4 into `r7`. `r7` is reserved for the system call number, and 4 happens to be the system call number for reading input from the keyboard. 

With all the necessary registers set, Robin calls the `svc` instruction with the `#0` parameter, which indicates that he wants to perform a system call. The kernel then takes over and reads input from the keyboard, storing the result in the buffer specified by `r1`.

Now that Robin has read input, he needs to send a message to his Merry Men, which he can do using the following code:

```
mov r0, #0   @ set to stdout
mov r1, r2
add r2, r2, #1   @ add 1 to size for null terminator
mov r7, #4   @ syscall write
swi #0
```

The first instruction sets `r0` to 0, indicating that he wants to write to stdout, the file descriptor that represents standard output. 

Next, he moves the length of the input buffer from `r2` into `r1`, making `r1` the second argument for the `write` system call.

Robin then increases the value of `r2` by 1 to account for the null terminator that will be added to the message.

Finally, he sets `r7` to 4, the system call number for writing output, and calls the `swi` instruction with the `#0` parameter to invoke the system call.

With these instructions, Robin is able to handle input and output in his adventure as a modern-day Robin Hood. And by learning these ARM assembly language instructions, you too can handle input and output in your own coding adventures!


[Next Chapter](06_Chapter06.md)