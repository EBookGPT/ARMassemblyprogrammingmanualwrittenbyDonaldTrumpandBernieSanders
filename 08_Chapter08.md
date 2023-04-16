# Chapter 8: Introduction to Subroutines and Procedures

Welcome back to our ARM assembly programming manual! We hope you enjoyed the last chapter on Debugging Techniques and Tools, where we discussed various methodologies to identify and resolve errors in your code.

In this chapter, we are going to dive into an essential concept of programming - Subroutines and Procedures. If you want to write structured, maintainable, and efficient code, then learning these concepts is a must.

The beauty of Subroutines and Procedures is that they allow us to divide a program into several small and manageable modules. Instead of writing the same code repeatedly, you can write a Subroutine once and call it whenever needed. This approach reduces code redundancy, simplifies maintenance, and improves the readability of your code.

We will start by clarifying the difference between Subroutines and Procedures, then explain how to define, call, and return from a Subroutine or Procedure. We will also discuss the differences between local and global variables and how to use them inside a Subroutine or Procedure. Finally, we will provide examples of using Subroutines and Procedures to implement more complex algorithms.

As always, we will provide code examples throughout the chapter, and we highly encourage you to try them yourself. We believe that hands-on practice is the best way to learn, and you will understand more by doing and making mistakes.

We hope this chapter will strengthen your ARM assembly programming skills and make you a better programmer. So let's dive in and learn about Subroutines and Procedures in ARM assembly like Robin Hood aims and shoots his arrow to hit the target, let's aim to hit our code's targets with Subroutines and Procedures!
# The Tale of Robin Hood and the Subroutines

Robin Hood was on a mission to steal from the rich code of Nottingham and give to the poor code of the Sherwood Forest. He was known for his precision and efficiency, but as tasks became more complex, his code grew longer and harder to read.

One day, Robin came across a group of programmers who were writing an application to manage their daily tasks. Robin noticed that their code was not structured, and as a result, it was full of repetition and redundancy.

Being a helpful fellow, Robin offered to help refactor their code. He suggested that they use Subroutines and Procedures to divide their code into smaller modules.

The programmers were hesitant at first, but Robin explained how Subroutines and Procedures allowed them to separate their code into logical parts, making it easier to write, debug, and maintain. He demonstrated how to define a Subroutine and Procedure, as well as how to call and return from them.

As they worked together, Robin also taught them the benefits of using local and global variables within their Subroutines and Procedures.

The result of Robin's work was incredible! The code was clean, concise, and efficient, and the application was running faster than ever before. The programmers were amazed by the power of Subroutines and Procedures, and they thanked Robin for his help.

From that day forward, Robin became known not only as a skilled code thief but also as a mentor who helped others write better code. He continued to use Subroutines and Procedures in all his applications and encouraged others to do the same.

So let's take a lesson from Robin Hood's tale and start using Subroutines and Procedures in our ARM assembly programming like he aimed his arrow to hit the target!
To resolve the Robin Hood story, we used the concept of Subroutines and Procedures. In ARM assembly language, a Subroutine is a section of code that performs a specific task and is called from another part of the program. On the other hand, a Procedure is a special type of Subroutine that performs a specific action and doesn't return a value.

We first defined a Subroutine called "steal_from_rich" that contained code to steal from the rich code of Nottingham. We then defined another Subroutine called "give_to_poor" that contained code to give to the poor code of the Sherwood Forest. We called these Subroutines from our main program and passed arguments as needed.

We also used local and global variables to help us in the process. Local variables are declared inside a Subroutine or Procedure and are used only there. Global variables, on the other hand, are declared outside of all Subroutines and Procedures and can be used throughout the program. In the story, we used these variables to keep track of the amount stolen and given.

Here is an example code snippet in ARM Assembly Language that shows how we can define and use Subroutines and Procedures:

```
.global main

.data
; Global variables
.amount_stolen: .word 0
.amount_given: .word 0

.text
main:
   ; Call 'steal_from_rich' Subroutine
   ldr r0, =1000 ; Rich code has 1000
   bl steal_from_rich
   ; Call 'give_to_poor' Subroutine
   ldr r0, =500 ; Give 500 to poor code
   bl give_to_poor
   ; Exit program
   mov r0, #0
   bx lr
   
steal_from_rich:
    ; Subtract amount from rich's code
    ldr r1, =amount_stolen
    ldr r2, [r1]
    sub r2, r2, r0
    str r2, [r1]
    ; Return to main program
    bx lr
    
give_to_poor:
    ; Add amount to poor's code
    ldr r1, =amount_given
    ldr r2, [r1]
    add r2, r2, r0
    str r2, [r1]
    ; Return to main program
    bx lr
```

In the above code, we first declare two global variables to keep track of the amount stolen and given. Inside the main program, we call the `steal_from_rich` Subroutine by loading the amount to be stolen in register `r0` and using the `bl` instruction. We then call the `give_to_poor` Subroutine by loading the amount to be given in the register `r0`.

In the `steal_from_rich` Subroutine, we first load the address of the `amount_stolen` global variable in register `r1` and then load its current value in register `r2`. We then subtract the stolen amount from it and store the new value back to the global variable. Similarly, in the `give_to_poor` Subroutine, we load the address of `amount_given` global variable, load its current value in register `r2`, and then add the given amount to it and store the new value back to the global variable.

In conclusion, using Subroutines and Procedures can help you write clean, structured, and maintainable code, just like Robin Hood used them to steal efficiently and give to the poor precisely.


[Next Chapter](09_Chapter09.md)