# Chapter 6 - Working with Arrays and Strings

Welcome back, my fellow programmers! We hope you enjoyed our last chapter on ‘Handling Input and Output’. We are pleased to present our next chapter on ‘Working with Arrays and Strings’. 

As you may already know, arrays and strings are fundamental concepts of programming, and knowing the ins and outs of handling them is critical to creating efficient code. In this chapter, we will dive deep into the world of arrays and strings, their anatomy, and how they function, and explore how we can work with them using ARM assembly language.

But before we get into the nitty-gritty details, a quick message from our friend Bernie:

"The power of programming lies in our ability to work with data structures like arrays and strings. Whether it's sorting, filtering, or searching for specific values, our coding skills must be sharp enough to deliver solutions to real-world problems that may arise. All too often, we forget these implications, but it's imperative to remember them so that we can continue to deliver life-changing solutions through our code!"

With that in mind, let's dive right into the wonderful world of arrays and strings with ARM assembly language!
# The Adventure of Robin, the String Hunter

Once upon a time, in the land of Sherwood Forest, there lived a notorious outlaw by the name of Robin Hood. Robin had a unique talent for hunting down the most cunning and elusive targets. But now, Robin was facing his greatest challenge yet- finding a particular hidden treasure whose whereabouts could only be described by a string.

Robin Hood was determined to find this treasure, but he needed your brilliant coding skills to accomplish his mission. Equipped with ARM assembly language and a string-processing tool, you and Robin Hood set off on an epic adventure!

As Robin and you traverse through Sherwood Forest, you come across a clearing where you see a group of people struggling to put their names in alphabetical order. Robin, already eager for his new challenge, steps up and offers your help.

`Start of Code Sample 6.1 - Sorting An Array Alphabetically in ARM Assembly`

```ARM
   AREA SortingAlphabetically, CODE, READONLY
  
   ENTRY
  
   ; Initialize Data
Names   DCD    Name1, Name2, Name3, Name4, Name5, Name6
Name1   DCD    0x526f6265 ; -> "Robe"
Name2   DCD    0x50657465 ; -> "Pete"
Name3   DCD    0x476f6c64 ; -> "Gold"
Name4   DCD    0x536d6974 ; -> "Smit"
Name5   DCD    0x5061726b ; -> "Park"
Name6   DCD    0x4d696b65 ; -> "Mike"
 
   ; Initialize Pointers
   LDR   R1,=Names
   LDR   R2,=Names+4
   LDR   R3,=Names+8
   LDR   R4,=Names+12
   LDR   R5,=Names+16
   LDR   R6,=Names+20
 
   ; Start of the Sort
Again
   ; Reset point to first name.
   LDR   R1,=Names
   LDR   R2,=Names+4
 
   ; Comparison loop for the sort.
Loop
   ; Does R3 < R2?
   LDR   R0,[R3]
   LDR   R12,[R2]
   CMP   R0,R12
   ; No -- Skip ahead
   BGT   SkipA
   ; Yes -- Swapping Pointer Values
   STR   R12,[R3]
   STR   R0,[R2]
SkipA
   ADD   R1,#4
   ADD   R2,#4
   ADD   R3,#4
   ADD   R4, #-1
   ; End Loop.
   CMP   R4, #0
   BNE   Loop
   
   ; End of Sort.
   SUBS  R4, R4, #1
   ; Test if any swaps were made
   LSL   R4, R4, #31
   MOVT  R4, #1
   BXEQ  LR
   B     Again
   END
```
As you execute the code, you notice the names on the list have all been sorted alphabetically. Robin Hood is ecstatic at the way you turned things around using your ARM assembly programming expertise!

You continue on your journey and come across a river, with no bridge. A few wooden logs lay scattered about, but none seem long enough to cross the river. After a careful look, Robin Hood discovered that one of the logs hides the length of the only log long enough to cross the river.

`Start of Code Sample 6.2 - Finding the Longest Log in a list of Logs in ARM Assembly`

```ARM
    AREA LogLength, CODE, READONLY
  
    ENTRY
  
    ; Initialize Data
Logs        DCD     Log1, Log2, Log3, Log4, Log5, Log6
Log1        DCD     "Five Meters"
Log2        DCD     "Six Meters"
Log3        DCD     "Three Meters"
Log4        DCD     "Ten Meters"
Log5        DCD     "Eight Meters"
Log6        DCD     "Four Meters"
 
    ; Create Pointers and Initializations
    LDR        R7, =Logs
    LDR        R8, [R7]
    MOV        R6, #0
       
Loop
    ; Increment Counter before we start.
    ADDS       R6, #1
    ADD        R7, #4
    LDR        R0, [R7]
    CMP        R0, R8
    ; If R0 is larger than R8, assign to R8
    BGT        Greater
    ; Else, end loop.
    BEQ        EndOfLine
    B          KeepGoing
 
Greater
    MOV        R8, R0
    MOV        R6, R6
    B          KeepGoing
 
EndOfLine
    B          BreakLoop
 
KeepGoing
    ; Continue Looping
    CMP        R6, #5
    BGT        BreakLoop
    B          Loop
 
BreakLoop
    ; Log Finished
    END
```
As you run the code, you find the correct length of the log, allowing Robin Hood and you to cross the river safely.

At last, Robin and you arrive at the location of the hidden treasure, but it's not over yet! The treasure's location is described as a string - a combination of characters, numbers, and symbols. To your surprise, Robin Hood pulls out an ARM assembly string parsing tool, specifically designed to extract a particular character from a string at a certain position.

`Start of Code Sample 6.3 - Parsing a string in ARM Assembly`

```ARM
   AREA ParsingAString, CODE, READONLY
  
   ENTRY
  
   ; Initialize Data
String     DCD    0x6f626c6f ; -> "oblo"
Position   DCD    2
 
   ; Perform the Parsing Routine
   MOV        R0, #0
   LDR        R1, =String
   LDR        R2, =Position
Loop
   LDRB       R3, [R1,R0]
   ADD        R0, #1
   ADD        R5, #1
   CMP        R5, R2
 
   ; Break When Character Found
   BEQ        CharacterFound
  
   ; Continue Looping
   CMP        R0, #4
   BNE        Loop
   B          NotFound
  
CharacterFound
   ; We found the character at index 2
   MOV        R6, #1
   B          Complete
  
NotFound
   ; We didn't find the character at index 2
   MOV        R6, #0
Complete
   ; Done.
   END
```
As you run the code, Robin Hood jumps in excitement as you extract the required character from the string regarding the hidden treasure.

With the string in hand and the location of the hidden treasure finally revealed, Robin Hood takes you to the treasure's location. While Robin Hood may have taken the treasure, the adventure of Robin, the String Hunter, reinforced your coding expertise in working with arrays and strings while having your fun with ARM assembly language!
# Explanation of the Code

The Robin Hood story has been solved using ARM assembly language. We wrote three code samples that helped Robin Hood and the programmer to achieve their goals.

## Code Sample 6.1 - Sorting An Array Alphabetically in ARM Assembly

In this sample, we initially declared an array of names that we wanted to sort alphabetically. This sample uses the Comparison Sort algorithm in order to sort the array in ascending order.

We first initialize the data by assigning all the names to a memory buffer using DCD. Then we create pointers that point to each name in memory. Further, we start by comparing the first two names and swapping them if the second name is smaller. Then, we compare the second and third names and swap them if required. We keep counting from the first to the last name until all the pairs have been compared and swapped if necessary. We repeat the entire algorithm until no more swaps have to be made.

## Code Sample 6.2 - Finding the Longest Log in a list of Logs in ARM Assembly

In this sample, we have six different wooden logs of varying lengths that Robin Hood and the programmer need to sort through to find the longest one. In this scenario, we check the length of each log by comparing it to the previous log's length, and then store the longest log's length.

We start by initializing the data and assigning the logs to a memory buffer using DCD. Then we create pointers that point to each log in memory. We check the length of each log by comparing it to the previous log's length. As we loop through each log, we keep counting until we have gone through all six logs. Finally, we output the longest log's length.

## Code Sample 6.3 - Parsing a String in ARM Assembly

In this sample, we have a string describing the location of the hidden treasure with an identifiable character at a certain position. In this scenario, we check whether the character is present at the specified index in the string.

We initialize the data by storing the string in a memory buffer using DCD, setting the index of the character we are looking for. We then start by looping through each character in the string individually. We compare each character's index from the string with the index of the character we are looking for. If the two indices match, we know that we have found the character we were looking for.

Thus, using these three samples of ARM assembly programming, Robin Hood was able to find the hidden treasure that would not have been achievable without the programmer's coding expertise. With Robin Hood's experience and the programmer's technical knowledge, together they were unstoppable, and their adventures in Sherwood Forest continued until their next mission!


[Next Chapter](07_Chapter07.md)