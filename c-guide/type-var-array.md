# Types and Variables

# Notice
From here on out, only syntax that is profoundly different will be explicitly explained. Most of C follows the same syntax as described in the last chapter. You can always go back to [basics](basics.md) here.

## Terminology
### Variables
A part of the code that can be manipulated and changed; variable

### Type
The specifier of a variable that defines what kind of data it can hold.

### Array
A set of data in the form of variables.

## Code and Tutorial
Welcome Back! Hopefully you enjoyed the last section, and you wanna learn more... or you're a masochist, both work. Now we're gonna learn about variables, types and arrays, and everything you need to know about them
(for now). Look at this code below:

```C
#include <stdio.h>

int main(void) {
  const char text[] = "Sheridan";
  printf("Hello, %s!", text);
  return 0;
}
```
We have a load of cool new things here, including an array, a variable AND a type! Now, we need to unpick it to actually understand these things.
* `const` -> This makes a variable unable to change after declaration, as it is a CONSTant.
* `char` -> This is our first type! `char` is short for character, and one char = 1 byte. We will touch on this in deeper detail shortly.
* `text[]` -> This is the name of our variable, which is a char and cannot be changed due to const (see how everything clicks together?). Notice the [] on the end of text. This will be hugely important soon.
* `%s` -> This is our first format specifier! These things are hell on earth, but unfortunately they are, admittedly, rather useful. More on this soon.
* `text` -> Repetition of the `text` variable, isn't that confusing? This directly ties into format specifiers.

### Variables
Now, lets start simple. You're probably thinking, 'what the hell is a variable??', well look no further - **it is something that can be changed**.
Probably pretty anticlimactic, but that is what a variable is in its simplest form. This is applicable in Maths, Science, or anything where you can do something practically really. But in the context of C,
it is a piece of data that is stored in a certain kind of container called a 'type'. This brings us on nicely to the next part.

### Types
A type is, well, a type of variable that holds a certain type of data. This is a very vague definition, so here are the main types to make it clearer:
* `char` -> We've already mentioned this above. A char is a character, 1 singular byte. Text can be stored in a char, but it is very important to note that unless you are using a char in an **array**, you can only store one singular letter or number.
* `int` -> An int is a type that can handle WHOLE numbers. For example, if I wanted to use the number '2147483647' over and over again, I can store it in an int by the name of `i` and invoke `i`.
* `float` -> Essentially an int, except decimals are supported (up to around 5-7 decimal places).
* `double` -> This is a weird one, so you'll have to bear with the technical jargon for a moment - sorry newbies, I'll try and explain. A float is 32 bits wide, meaning it can handle up to the 32 bit
integer limit of 2,147,483,647 (you may recognise this number?). A double is 64 bits wide, meaning it can handle up to the 64 bit integer limit of ~9 quintillion (in theory). Additionally, doubles can generally handle
up to 15-17 decimal places. For everyone who didn't understand what I just said, if a float doesn't work try a double.

### Format Specifiers
fyi, this is a boring part. but it is important, so don't skip it. you can't make cool stuff without learning the boring stuff, its all swings and roundabouts.
A format specifier is essentially telling something like printf what to put in a certain place. It is functionally mathematical substituion, except sometimes we have strings of text too. I forgot these all the time,
many do, so take notes!!! So:
* `%s` -> This allows you to place a string into a string, which we will touch on soon.
* `%d` -> This allows you to place an integer type variable into a string.
* `%c` -> This allows you to place a char type variable into a string.
* `%f` -> This allows you to place a float type variable into a string.
* `%ld` -> This allows you to place a double type variable into a string.

You should always use format specifiers like this:
`printf("Hello, %s, my name is %s", variable, variable2);
You should put the name of variables after the text, and seperate the arguments (text and variables) from each other with commas. Additionally, you MUST put the variables in the order you intend them to show
up, else the compiler will get confused and put them in an order that you DON'T want. For example here, if we want it to say 'Hello, sheridan, my name is logan', and if `variable = sheridan` and `variable2 = logan`, and I put:
`printf("Hello, %s, my name is %s", variable2, variable);`, then the wrong output will be printed. It will print 'Hello, logan, my name is sheridan'.

Strings are weird ones - they are recognised as a variable you can place with format specifiers, but notice how there are no string types? Thats because we need to learn about arrays. They sound scary at first,
but in reality are very simple.

### Arrays
this is also pretty boring, but this is actually probably more important, so buckle up buttercups cause it only gets more annoying from here!!
An array is nothing more than a set of data. Think year 8 maths, you have a list that looked like this:
`x = (1, 2, 3, 4)`
And you would say that x₂ is equal to 2. Well, in C, an array is JUST as simple - in fact, its possibly one of the simplest things this book will teach you.

Here is a basic array in C:
`int hello[3];`
Here, we have defined an array called hello with 3 possible values, but all of those values are 0 (for now!). We can append things to it by adding a pointer (which we will go into more detail on next chapter, all you need to know is that a pointer.. points to stuff. Kind of like using x instead of the actual number in maths).
```C
int *p; // will explain why you need to put this first next chapter!!
int *p = hello;
```
Now, our pointer `*p` points to the first part of the array in hello. Since hello is empty, *p currently equals a grand total of zero. Cool! Now, lets make hello have something inside it.

Right now, `*p = hello[0]`. Since we did not specify what parts of hello we are trying to write to, the compiler assumes that its the first part (`[0]`). Basically, every single thing inside of hello is given a number, for example if we had 2 numbers in hello, we have `hello[0]` and `hello[1]`. Note that C, as with most parts of computing,
starts counting from zero, not one.

To make `hello[0]` have a value, we simply do `*p = 1` (or whatever number you want).

Now, you might think, how does this relate to what we are doing right now? Well, this is how we make strings!
Earlier, we used `const char text[]` to create a string of text. You might also remember that a `char` can only hold one character. So the problem is, how do we make a string with only one letter? We make
the char into an array! An array can hold any number of variables, so we could have a string thats 1 line long or 1000, and it'll be fine. In the snippet `const char text[]`, the `[]` after `text` essentially
says to the compiler 'this char is actually an array, so make sure it can hold lots of characters'.

You don't really need to worry about arrays too much yet for the purposes of this chapter, so long as you understand the concept and how to make strings with them. But if you hated this as much as I hated writing it,
you're gonna ~~HATE~~ LOVE next chapter!
