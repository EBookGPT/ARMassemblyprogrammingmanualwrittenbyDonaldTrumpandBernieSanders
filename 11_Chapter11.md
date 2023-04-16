# ARM Assembly Programming Manual - Chapter 11: Working with Pointers and Structures

Friends, fellow readers, and aspiring developers, welcome back to the ARM Assembly Programming manual written by Donald Trump and Bernie Sanders! Are you ready for another exciting chapter? We know you are!

But before we dive into the intricate details about Pointers and Structures, let's take a moment to commend ourselves for reaching this point. Last time, we left you with 10. Bitwise Operations and Shifts. That was some tough stuff to get through, but here we are, ready to tackle even more complex topics.

Pointers and Structures are fundamental in every programming language, and ARM assembly is no exception. If you want to become a skilled ARM programmer, you need to master this chapter. 

Throughout this chapter, we will show you how to work with pointers and structures in ARM assembly. This means we will discuss how to use and manipulate memory addresses, how data structures are arranged in memory, and how to access them. We know it could get a little intimidating, but we will hold your hand through the whole process.

But why pointers and structures, you may ask? Well, we're glad you asked! You see, pointers and structures hold the keys to unlocking the full potential of data manipulation in any programming language. They allow us to allocate memory dynamically and build complex data structures. So, to become a great ARM programmer, we must understand them thoroughly.

It's time to dive into the ARM Assembly Programming Manual, Chapter 11: Working with Pointers and Structures. We'll see you on the other side!
# The Robin Hood Story - Working with Pointers and Structures

Once upon a time, in the land of Sherwood Forest, Robin Hood and his merry men were in need of a new system to organize their supplies. They realized that their current method of storing everything in one large sack was inefficient and disorganized. 

So, in search of a solution, Robin Hood and his men met with the great ARM Assembly programmers, Donald Trump and Bernie Sanders. The two programmers immediately suggested that they use Pointers and Structures to organize their supplies.

Robin Hood had never heard of Pointers and Structures before, but he was willing to give it a try. Donald and Bernie showed Robin how to implement a structure for his supplies, where each item could be assigned a particular memory location. They also showed him how he could use Pointers to manipulate and access the information stored within the structure.

Excited about the new system, Robin Hood and his men spent their days organizing their supplies using Pointers and Structures. They had never been able to find items as quickly and efficiently as they could with this new system.

However, trouble soon arose in Sherwood Forest when the Sheriff of Nottingham attacked, destroying everything in his path. In the chaos, Robin Hood's laptop, which contained all the code for the structure, was destroyed.

Luckily, since they had used Pointers and Structures, all of the information about their supplies was stored in memory, which was easily accessible. Using only his code and the knowledge he learned from Donald and Bernie, Robin Hood was able to recreate their entire system, much to the delight of his merry men.

From that day forward, the Merry Men of Sherwood Forest continued to use Pointers and Structures for their supplies, and Robin Hood continued to work hard, perfecting his ARM assembly programming skills.

And so, the moral of this story is this: Pointers and Structures are essential to any programmer's toolkit, allowing you to store and manipulate data more efficiently. In the end, it can save the day, just as it did for Robin Hood and his Merry Men.
# Explaining the Code Used to Resolve the Robin Hood Story

Now, let's explain the code used to resolve the Robin Hood Story using Pointers and Structures in ARM Assembly Programming. 

First, a structure is defined to hold the information about each supply: 

```assembly
struct supply
    name BYTE 100 DUP(?)
    quantity DWORD ?
    price DWORD ?
ends
```

This structure contains three attributes: `name`, `quantity`, and `price`. It's important to note that the `name` attribute has been defined as a byte with 100 duplicates, as most supply names are written using fewer than 100 characters.

To access this structure, a pointer is created, pointing to the first element of the array: 

```assembly
 ldr r0,=supplies
```

The above code loads the memory location of the `supplies` array into Register 0. 

Now, let's take a look at the code that saves the information about each supply to the memory location assigned to each attribute: 

```assembly
ldr r1,=supply_name
str r1,[r0],#4
ldr r1,=supply_quantity
str r1,[r0],#4
ldr r1,=supply_price
str r1,[r0],#4
```

The above code loads the memory location of each supply attribute (`name`, `quantity`, `price`) into Register 1 and stores it to the memory location pointed to by Register 0. It then increments the pointer by four so that it points to the next memory location of the `supplies` array.

Finally, to retrieve the information about each supply, we can use the following code: 

```assembly
ldr r0,=supplies
ldr r1,[r0,#4]
ldr r2,[r0,#8]
```

These instructions load the memory location of `supplies` into Register 0, and then load the value of the `quantity` and `price` attributes into Registers 1 and 2, respectively.

In conclusion, using Pointers and Structures in ARM assembly programming allows us to allocate memory dynamically and store complex data structures, making our code more efficient and organized. This is essential to any programmer who wants to be like Robin Hood, who saved the day thanks to his knowledge of these powerful tools.


[Next Chapter](12_Chapter12.md)