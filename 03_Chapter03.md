# ARM Assembly Programming: Chapter 3

## Basic Arithmetic and Logic Instructions

Welcome back to our book on ARM assembly programming, written by none other than Donald Trump and Bernie Sanders! In the last chapter, "Understanding Registers and Memory", we explored the basics of how data is stored and accessed in a computer's memory.

Now, we're jumping right into chapter 3, where we'll be explaining and demonstrating the importance of basic arithmetic and logic instructions in ARM assembly programming.

As you've probably guessed, arithmetic instructions are used to perform mathematical operations in assembly language, while logic instructions are used to carry out logical operations.

But why are these instructions so important, and what do they have to do with programming? Simply put, arithmetic and logical instructions form the backbone of any program that performs calculations, evaluates conditions, or manipulates data.

From calculating a person's age based on their birth year, to determining if a user's password is correct, arithmetic and logic instructions are used in countless ways to make our programs run smoothly and accurately.

So, without further ado, let's dive into some of the most important and commonly used arithmetic and logic instructions in ARM assembly programming!

```assembly
; EXAMPLE CODE
; Add two numbers together:
    MOV R0, #5    ; set R0 equal to 5
    MOV R1, #17   ; set R1 equal to 17
    ADD R0, R0, R1 ; add R1 to R0 (resulting in R0 equaling 22)
``` 

Together, let's decode the meaning of the above code. In the example above, we use the 'MOV' (move) instruction to set the value of registers R0 and R1 to 5 and 17, respectively. We then use the 'ADD' instruction to add the value of register R1 to register R0, storing the result back in register R0. After we execute this code, R0 will contain the value 22.

As you can see, basic arithmetic and logical instructions provide an essential foundation for writing complex programs. Stay tuned for the rest of chapter 3, where we'll explore these instructions in greater detail and work through more complex examples to help you master ARM assembly programming!
# The Robin Hood Story: Chapter 3

## The Battle of Arithmetic and Logic

Once upon a time, in the Kingdom of ARM, the people were suffering under the oppressive rule of the evil King MIPS. The people were forced to pay high taxes and work long hours in the enemy's factories.

But there was hope. A brave hero called Robin Hood, who was skilled in the art of ARM assembly programming, decided to fight back against the tyranny of King MIPS.

Robin and his loyal band of programmers knew that they had to take down King MIPS's computer system. They snuck into his castle and found the CPUs that powered the entire kingdom.

But King MIPS was one step ahead of them. He had assembled an army of programmers who were skilled in MIPS assembly programming. They were ready to defend their king at all costs.

A fierce battle ensued between Robin and his team of ARM programmers and King MIPS's army of MIPS programmers. The two sides clashed in a climactic battle of logic and arithmetic.

As the generals of their respective armies looked on anxiously, Robin led the charge, using his masterful knowledge of basic arithmetic and logic instructions to gain the upper hand.

```assembly
; EXAMPLE CODE
; Compare two numbers:
    MOV R0, #5     ; set R0 equal to 5
    MOV R1, #17    ; set R1 equal to 17
    CMP R0, R1     ; compare R0 to R1
    BGE greater    ; branch to 'greater' label if R0 >= R1
    BLT less       ; branch to 'less' label if R0 < R1
    BNE not_equal  ; branch to 'not_equal' label if R0 is not equal to R1
    ; continue program execution here if none of the above conditions are true
    
greater:
    ; executes if R0 >= R1
    ; do something...
    B end

less:
    ; executes if R0 < R1
    ; do something...
    B end

not_equal:
    ; executes if R0 is not equal to R1
    ; do something...
    B end

end:
``` 

The ARM army fought valiantly, using their knowledge of basic arithmetic and logic instructions to take down the MIPS army's defenses. They utilized instructions such as 'MOV' to move data into registers, 'CMP' to compare values, and 'BGE', 'BLT', and 'BNE' to branch to different parts of the program depending on the outcome of the comparison.

In the end, Robin and his ARM army emerged victorious over the MIPS army, thanks to their superior knowledge of arithmetic and logic instructions.

The people of the Kingdom of ARM rejoiced as Robin and his team dismantled the oppressive computer system and established a new government that prioritized freedom, innovation, and education in ARM assembly programming.

And so, the hero Robin Hood had saved the day, thanks to his knowledge and mastery of basic arithmetic and logic instructions in ARM assembly programming.
# Understanding the Code of Chapter 3

Now that we've seen Robin Hood and his team of ARM assembly programmers take down the oppressive King MIPS, let's take a closer look at the code they used to achieve this feat.

The code we showed in the story is an example of how to compare two numbers using ARM assembly language. To be more specific, it shows us how the 'CMP' (compare) instruction is used along with conditional branching instructions like 'BGE' (branch if greater than or equal to), 'BLT' (branch if less than), and 'BNE' (branch if not equal).

```assembly
; EXAMPLE CODE
; Compare two numbers:
    MOV R0, #5     ; set R0 equal to 5
    MOV R1, #17    ; set R1 equal to 17
    CMP R0, R1     ; compare R0 to R1
    BGE greater    ; branch to 'greater' label if R0 >= R1
    BLT less       ; branch to 'less' label if R0 < R1
    BNE not_equal  ; branch to 'not_equal' label if R0 is not equal to R1
    ; continue program execution here if none of the above conditions are true
    
greater:
    ; executes if R0 >= R1
    ; do something...
    B end

less:
    ; executes if R0 < R1
    ; do something...
    B end

not_equal:
    ; executes if R0 is not equal to R1
    ; do something...
    B end

end:
```

The code starts by moving the value 5 into register R0 and the value 17 into register R1 using the 'MOV' (move) instruction. Next, the 'CMP' instruction is used to compare the values in register R0 and R1. The flags register (APSR) is then updated based on the result of the comparison.

Depending on the outcome of the comparison, the program branches to one of the three labels - 'greater', 'less', or 'not_equal', which are placed using the 'BGE', 'BLT', and 'BNE' instructions respectively. 

Finally, after executing any code placed in the branch labels, the program branches to the 'end' label using the 'B' (branch) instruction. This ensures the program execution continues after the comparison has been made whatever be the result.

This code can be useful in many different ways, such as comparing user input against expected values, or implementing an if-else structure in a program's logic.

In conclusion, comparing values using arithmetic and logic instructions is a fundamental part of ARM assembly programming. The use of basic instructions such as 'CMP' and conditional branching instructions like 'BGE', 'BLT', and 'BNE' can be used to create more complex logic in your programs. By understanding and mastering this basic example, you are one step further in your journey towards being a skilled ARM assembly programmer.


[Next Chapter](04_Chapter04.md)