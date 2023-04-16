# Chapter 4: Branching and Looping Instructions

Welcome back, folks! We hope you enjoyed learning about basic arithmetic and logic instructions in our previous chapter. Now, it’s time to take things to the next level with branching and looping instructions.

As always, we’re here to teach you how to code like a pro. These instructions will allow you to make your code more efficient by jumping to different parts of the program or repeating a set of instructions multiple times. 

It’s important to learn how to use these instructions because they’re essential for writing complex programs. 

So sit tight, grab a cup of coffee, and let’s dive into the world of branching and looping instructions. Don’t forget to take notes and ask questions if you need help - we’re here to help you every step of the way.

Are you ready to become a branching and looping master? Let’s get started!
# The Tale of Robin Hood's Heist

Once upon a time, Robin Hood and his band of merry men had a daring plan. They wanted to steal from the wealthy Prince John and his men, and give the spoils to the poor villagers.

However, they knew it wouldn’t be easy - Prince John’s castle was heavily guarded, and it would require some quick thinking to execute their plan.

Robin Hood had a plan. He told his men to sneak into the castle during the prince's birthday celebration, when the guards were busy feasting and drinking. But they needed to be careful. They would have to move quickly and avoid detection. 

To do that, they used ARM assembly programming and implemented some branching instructions to help them navigate the castle undetected.

```
Loop:
    CMP r2, #0 ;check if guards are still around
    BEQ EndLoop ;if no guards, exit loop
    MOV r1, #0 ;stealthily move
    SUB r2, #1 ;decrement guard count
    B Loop ;repeat loop
EndLoop:
```

They used a loop to keep checking if there were any guards patrolling the area. If there were guards, they moved carefully and silently, making sure not to be detected.

But they also used a branch instruction to make sure they’d exit the loop when all the guards were gone.

```
CMP r1, #5 ;check if wine is too heavy
    BGT TooHeavy ;if too heavy, exit loop
```

As they wandered deeper into the castle, the band of thieves came to a room filled with treasure. However, the chest containing the most valuable items was guarded by another group of soldiers.

Robin Hood realized they couldn't defeat them in a fight. Instead, he used a branch instruction to make a quick escape. 

```
CMP r1, #0 ;check if guards are still chasing
    BNE Escape ;if so, escape
    MOV r2, #1000000 ;start counting money
    B EndLoop ;leave with spoils
Escape:
    BL Exit ;end the program
```

Thanks to their expertise in ARM assembly programming, they were able to create a clever escape plan, using branching instructions to outwit the guards and escape with the valuable treasure.

When they made their way back to the village, they distributed the treasure to the poor inhabitants, leaving them filled with hope and prosperity. 

And so, Robin Hood and his band of merry men continued to use their ARM assembly programming skills to execute successful heists and keep the people of the village safe from harm.
# Explanation of ARM Assembly Code

In our Robin Hood story, we saw the use of branching and looping instructions to help Robin Hood and his band of merry men navigate the castle and execute their successful heist.

Let’s break down some of the code used in the story:

## Looping Instructions

Robin Hood’s team used a loop to repeatedly check if there were any guards still present in the area. They used the instruction `CMP` to compare if the value in `r2` was equal to `0`. If there were no guards present, they used the instruction `BEQ` to jump to the label `EndLoop` and exit the loop.

```
Loop:
    CMP r2, #0 ;check if guards are still around
    BEQ EndLoop ;if no guards, exit loop
    MOV r1, #0 ;stealthily move
    SUB r2, #1 ;decrement guard count
    B Loop ;repeat loop
EndLoop:
```

## Branching Instructions

In the story, our heroes also used branching instructions to make decisions based on the current state of the program. For example, when Robin Hood’s team encountered a room filled with treasure but guarded by another group of soldiers, they used branching instructions to make an escape plan.

They used `CMP` to compare if the value in `r1` was greater than `5`. If it was, they used `BGT` to branch to the label `TooHeavy`, which had instructions to help them retreat. If it wasn’t too heavy, the program would continue with the following instructions without branching.

```
CMP r1, #5 ;check if wine is too heavy
    BGT TooHeavy ;if too heavy, exit loop
```

Robin Hood's team also used the `CMP` instruction to compare if guards were still chasing them. If they were, they used `BNE` to branch to the label `Escape` and make a quick escape from the castle.

```
CMP r1, #0 ;check if guards are still chasing
    BNE Escape ;if so, escape
    MOV r2, #1000000 ;start counting money
    B EndLoop ;leave with spoils
Escape:
    BL Exit ;end the program
```

## Summary

Branching and looping instructions are essential for creating complex programs. As we saw in the Robin Hood story, they can be used to navigate a space, make decisions based on program states, and quickly plan an escape from danger.

When you’re coding, it’s important to use these instructions wisely to take full advantage of ARM assembly programming.


[Next Chapter](05_Chapter05.md)