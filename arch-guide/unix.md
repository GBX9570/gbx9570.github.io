# Unix in Linux
In the Linux and wider OS community, you hear 'Unix this', 'Unix that'. But you might wonder what Unix actually is, and why it's so popular.

# What is Unix?
Waaaaaay back in the 70s, every computer worked differently. They all had different architectures and every operating system and program was written in Assembly (a language
that is specific to an architecture, and still exists today, but is much less heavily relied upon). Operating systems also all worked quite differently, meaning that the
knowledge of one operating system may not or probably will not transfer to another. This made vendor lock in completely unavoidable - levels that Apple can only dream of.  
  
So, the first step to solving this was creating the ~~begrudged~~ beloved programming language C, created by Dennis Ritchie. C was very different to Assembly, as it could
be compiled to run on any machine, and an operating system written in C would only have to make minor changes to run on a different architecture. The first operating system
to take advantage of this was Unix - written by Ritchie himself and Ken Thompson. Unix had many design choices that still hold true to this day - like the idea that 'everything
is a file'. Additionally, it is a relatively simple system, and the way it works is well defined in the POSIX standard (which emerged later on in the 80s).  
  
Ever since, operating systems have been based on Unixfor its developer friendly environment and its ease to implement. That's why Linux and Darwin (what macOS, iOS, watchOS, tvOS, etc etc are based off of) are 'Unix-Likes', or
more specifically, an operating system that aims to replicate Unix functionality without actually being Unix.  

# What does this mean for me now that I use Linux
It means you get to make use of the many brilliant thinks Unix brings to the table - and fight the slightly more frustrating things  

One cool feature that you can use with Linux and Unix is pipes. A command like lspci may bring up a massive string of text like so:  

```
user@computer ~ $ lspci
00:00.0 Host bridge: Intel Corporation Haswell-ULT DRAM Controller (rev 0b)
00:02.0 VGA compatible controller: Intel Corporation Haswell-ULT Integrated Graphics Controller (rev 0b)
00:03.0 Audio device: Intel Corporation Haswell-ULT HD Audio Controller (rev 0b)
... (thank you to [this site](https://dassencio.org/75) for publishing an lspci output
user@computer ~ $
```

but with pipes, you can use 2 commands at once to perform more than 1 thing. For example, I can run `lspci` and pipe in `grep` to create the command: `lspci || grep` (the `||` is called a pipe) to
end up with this output:
```
user@computer ~ $ lspci || grep "Audio"
00:03.0 Audio device: Intel Corporation Haswell-ULT HD Audio Controller (rev 0b)
user@computer ~ $
```

That is INCREDIBLY useful, and cuts down time looking through kernel logs with things like dmesg by instantly finding the terms you need.  

Additionally, any development tools of any kind will always prefer a Unix environment - apart from win32 tools, but that is an ABI that is comparable to Hell itself, so we are glad not to have it.
GCC, Clang, nasm, make, GNU Coreutils, etc etc are all designed to target Unix-like environments (like Linux, like macOS), and while Windows ports do exist, they always emulate a Unix environment to
keep the transition relatively simple.  

Furthermore, Unix has a principle of 'Do one thing, and do it well'. So you will not end up with a mess like the Windows Start Menu, that tries to be an app finder, file manager, web browser and file manager
searcher all in one in an extremely buggy conglomeration of old code and new code, you will get apps like nano or micro or neofetch or htop which do one thing (edit text, show system information, show
system statistics (like temperature and running tasks) respectively) very very well.  

Now there are some things that Linux have which other Unix likes might not have. For example, most Linux distributions use GNU utilities. This means they use the gold standard implementation of things like
`ls`, `cd`, `grep`, `dd`, etc etc. macOS and BSD operating systems use their own coreutils, which may be buggy or work in slightly different ways than what programs expect. While other coreutils implementations
exist for Linux (like busybox, rust-utils), GNU is the standard.  

And as a little bonus, the Linux community is a thriving corner or the tech community. Linux's open source nature encourages users to make and create anything, and theres so many cool tools and games and apps
that aren't made to suck money out of your bank account, but purely for the developers enjoyment and for yours too.  

# I don't know what you're saying to me
tl;dr - Linux is good for programming, you get some damn good, FREE software (mostly) and you get the best of the technical computing world.  

Thanks for reading this guide!
