# The Basics of the C language

## Terminology
### Compiler
A compiler is the software that takes your code and turns it into an executable program. For example, on a modern Linux system, I'd run:
`gcc hello.c -o hello`
to give me an executable file, and if all goes well, I should get a file named 'hello' and I can run with `./hello`

### Software
A piece of code that performs a specific function.

### Function
A piece of code in a program that does one function, and can be used in other functions.

## Code and tutorial

Below is the most basic program you can ever write in C:

```C
int main(void) {
  }
```

This program does... nothing. But it teaches us some important things very quickly:
* Where return types go in C
* How functions are declared, and their arguments
* How functions are opened and closed.

Lets take the first line:
`int main(void) {`
This likely looks like pure giberish, with no meaning. But every part of this line tells the **compiler** a key thing about this block of code. 
* `int` -> The return type. You will learn more about types later, but for now just know that this means when this function ends, it gives a number to whatever takes over after (whether its another function or the operating system).
* `main` -> The function name. This can be changed in every function to whatever you want*, but the main function is required to tell the compiler where to start from.
* `(void)` -> Every function takes arguments. The main function is no different. Arguments, like types, will be explained later. All you need to know is `void` means there are no arguments necessary for that function.

Now for the syntax. The return type must ALWAYS come before the function name, and the function name must ALWAYS come before the arguments. Additionally, the body (main part of the code) of the function is opened with a { and closed with a }.
Essentially, always follow this when declaring functions:
`type name(argument) { }`

Now lets move onto something slightly more ambitious. This will truly blow your mind with its complexity and its incredible output:
```C
#include <stdio.h>

int main(void) {
  printf("Hello, World!");
  return 0;
}
```
Thats right, we are printing hello world. You'll notice that the main function is identical, just with some new code. The main function is always the same, no matter the operating system or compiler (assuming the compiler supports C99+, but that is
unnecessary semantics). Now, we have some new language:

* `#include` -> This is called a preprocessor directive. Sounds scary, but in practice its rather simple. Essentially, it tells the compiler 'I want you to do this rather than me.'. During compilation (the process of compiling code into an executable program),
the preprocessor (the thing that reads your code and looks for preprocessor directives) carries out whatever you ask it to do. `#include` literally means, 'include this file of code so I can use it in my code.'.
* `<stdio.h>` -> This is part of the `#include` directive. This is a file from the C standard library - a bunch of files that includes functions premade for you to use. By importing the specific file `stdio.h`, we get access to things like `printf` or
`scanf` (which will be explained soon).
* `printf` -> This is a function that prints text to the screen. Simple enough. Remember how in the main example, I mentioned how every function has arguments? This is where that comes into play. The `("Hello, World!");` part is actually an argument.
It tells printf 'I wanna type this text to the screen.'. Arguments do get more complex, but this is one of the ones you'll use the most.
* `return 0;` -> This is where the return type comes into play. 0 is a number, therefore it is an integer. In most operating systems, if the main function returns the number '0', it is concluded that the program ran without any errors. You don't really need
to know the intricacies of how this works behind the scenes, as that leans into operating system development and systems enginerring, but if your curious: [Exit Statuses](https://en.wikipedia.org/wiki/Exit_status)

Additionally, we also have some new grammar! Before, functions started and ended with { and }, so now there must be some clarification.
You can both declare a function `type name(argument) {}` and invoke a function `name(argument);`. When declaring a function, you are putting the code inside of it manually and defining what the function can do. When invoking a function, you are either using
another function that you have written or someone else has written to perform a specific task. For example, I can declare the main function, and then invoke the printf function inside it to print text to the screen. This is the difference between declaration
and invocation. To continue, you might have noticed that invoked functions like return and printf end in semicolons. In C, this is how you tell the compiler that a line has ended. Without this, the compiler will give you an error like:
```bash
[user@computer ~]$ cc hello.c
hello.c: In function ‘main’:
hello.c:4:32: error: expected ‘;’ before ‘return’
    4 |         printf("Hello, World!")
      |                                ^
      |                                ;
    5 |         return 0;
      |         ~~~~~~
[user@computer ~]$
```

# What next?
That's it! You've completed the hardest part of your programming journey - paying attention to a full page of a guide. Now you have many many more to go through. Good luck!

* You can name any function whatever you want, so long as its not the same name as another function imported in the same file. You cannot have 2 printf's, for example.
