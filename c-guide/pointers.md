# Pointers

# Terminology
## Pointer
A variable that points (POINTer!!) to the memory address of another variable.

# Required Knowledge
A new section of the book! This won't be in every page, but it is DEFINITELY necessary to say here that if you don't understand arrays, jump on back to [chapter 2](type-var-array.md) and read through it all again till it makes sense. You'll thank me.

# Code and Tutorial
Hello again! I'm sure you've enjoyed your break.. no, your a C developer, breaks from your computer aren't a thing for your kind.

Now, everyone makes pointers look scary, with `*p` and `&x` and all that fancy stuff. Well, I'll explain it simply as I can!
Imagine you have a proxy email address. For those unfamiliar, its an email that sends stuff to your main email for extra security. Everything that gets sent to the proxy is given straight to your main email,
and anything sent from your main email goes through the proxy and to the intended receiver. That makes sense, pretty simple in concept. That's literally all that a pointer is.

Imagine you have a variable, `x`. Now, you need to use that variable elsewhere, so you setup a proxy - our pointer. `*p` is essentially a proxy email - it points to your main email, and returns from your
main email. In the case of C, it points to `x`, and returns from `x`. If `x = 2`, and you say `int *p = &x` (don't worry about the `*` and the `&`, I'll explain momentarily), then running:
`printf("%d", x);` and `printf("%d", *p);` will return the exact same thing.

Now some of the sharper among you may wonder, 'Why do we need proxies in C? No one is hacking into my variable.' - and yeah, you'd be correct. But it is SO much more than a proxy. Before I show you why, let
me explain some things.

You are probably wondering, 'why the funny symbols like `*` and `&`?'. Fair question, and a *simple answer. Basically, if you put a `*` BEFORE a variable, NEVER after, it becomes a pointer. If you put an `&`
BEFORE a variable, NEVER after, it becomes the memory address. Sounds complex.
Basically, `x = 42.` `&x = 0x736865726964616E` or whatever the hell your operating system decides to make it. In your head, you just have to think of this as '`x` = 42, `&x` = `x`'. I'm only telling you about
the memory addresses part because SOMEONE in the 70s decided that its important.
You already understand pointers, and the backend reasoning is practically irrelevant unless you wanna make a compiler - and this isn't a guide to writing a compiler. All you need to know is that `*p` = pointer
called p.

The fancy, technical, and much more convenient term for making a pointer point to the memory address of a variable (`int *p = &x;`, for anyone that forgot) is **dereferencing**. Dereferencing is essentially
saying to the computer 'hi, I would like to see what is stored in this memory address and be able to manipulate it.', rather than saying 'here is the raw memory address, deal with it'. This makes much more
theoritical sense on why changing a pointer changes the original variable, because before it likely seemed like magic. It's nothing more than editing the value.

Now, here is an example:

```C
int x = 42;
int *p = &x; // *p now points to the memory address of x.
*p = *p + 1; // this changes both *p and x
printf("%d", x); // returns 43, because we added 1 to *p
printf("%d", *p); // also 43.
```

It is important to note - you CANNOT say `*p = 42;`, or anything of the sort. 42 is a raw integer, and `*p` requires a memory address like &x.

Now, its time to bring arrays into the mix. This is one place where pointers really shine, because its the easiest way to manipulate a specific element of an array. You literally just do:

```C
int example[] = {1, 2, 3};
int *p = example; // since we didn't specify what element (by doing [0], [1], or [2]) the compiler assumes [0]. also, example[] = example after declaring it
*p = 20;
printf("%d", *p); // prints out the first element of example (example[0]), or 20. notice how changing the number with *p = 20 changed example[0]. this is dereferencing in action!
// also, fyi, if you do int *p = &example[x] then whatever you do to *p changes example[x], it doesnt have to be just zero
```

There are many uses for pointers, but rather than go on and on
about all the uses without ever explaining them or making this page hundreds of lines long with examples, I'm gonna show you as the guide goes on - and eventually, I'll explain things like double and triple
pointers (little bit more of a brainf*ck, but thats what you signed up for!).

There, thats all! You understand pointers. Far less scary than people make them out to be - remember kids, bad explanation makes things hard, not the topic!!
