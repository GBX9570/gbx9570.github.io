# Variable Manipulation
## Incrementing
Increasing the value of a variable.
## Decrementing
Decreasing the value of a variable.
## Scope
A part of the code where variables are valid. If you declare a variable in one function, it is available in that functions scope, but not anothers.

# Tutorial and Code
Welcome back to another episode of late 70s computer semantics!!! Today, we're gonna look at manipulating variables and changing what they do, what they hold and everything about them. There are so many reasons you'd wanna do this, because unlike in the examples shown before, variables are almost NEVER static in practice.

## Incrementing a variable.
Lets say you have an integer called `x`, and `x = 16`. How would you make `x` go up by one? Well, you would do `x = 17;`, which is perfectly acceptable. But what if you repeat `x = 17;` many times throughout the code, and then you change the original value of `x` from `16` to `32`. Now you have to go through EVERY SINGLE `x = 17;` in the scope and change it to `x = 33;`. This is slow and annoying. Alternatively, you can replace `x = 33;` with `x++;`, which adds one to `x` automatically. You can also do `x + 1;`, if you prefer a more verbose method, but `x++;` is cleaner.

## Decrementing a variable.
Literally the exact same as incrementing, except `x++;` becomes `x--;`. You can also do `x - 1;`.

Now you probably are thinking, 'when will i EVER need to increment something by one??', which is perfectly fair. So here is an example to make it clear:

```C
int strlen(const char *str) {
  // notice how *str is a pointer, because it has more than one character
  int counter = 0; // creates an integer called counter and sets it to zero
  if(*str) { // if the string *str isn't empty or ended, do this
    counter++; // increment counter by one
    str++; // increment *str by one
  }
  return counter; // make the return of this function the total held in counter
}
```

What this basically does is go through every single letter in the string `*str`, count how many letters there are and return it. When we do:
```C
if (*str) {
  counter++;
  str++;
}
```
We are basically saying 'if `*str` has something in it, or we aren't at the end of the string, make counter go up by one and go to the next letter of `*str`.' Simple enough. `if(*str)` literally means 'if `*str` has something in it'.
This is where we loop back to arrays. Remember when I said a string is actually just an array? Well, doing `str++` is actually just doing 'go to `str[0]`, now go to `str[1]`, etc etc'. This also means that if you have a pointer set to an array, you can do `p++;` (assuming the pointer is called `*p`) to go to the next part of the array. ALSO when you are messing with pointers, you drop the `*`. Annoying, I know. If you have `*p`, you CANNOT do `*p++;`, you MUST do `p++;`. This catches me out ALL THE DAMN TIME. I hate it.

TO BE CONTINUED
