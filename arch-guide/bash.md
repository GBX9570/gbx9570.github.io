# Bash to Basics
No matter how complex the topic may be, it's always good practice to briefly talk about the most basic parts of the topic. This guide is no different.
Out of the box, Arch uses bash, which can be proven by running `echo $SHELL` in the terminal. This guide only covers the basics of using the terminal and
using bash, because that's a whole topic in of itself. But, you will learn how to use the terminal.

# How do commands work?
Commands are typically broken down into two sections - command, and argument.
A command is something like `ls`, you type it and it performs an action. However, a command can be given an argument. This means you want that command
to do a different or specific action. For `ls`, you may give the argument `-la`, which comes together to make `ls -la`.

# Basic terminal commands
`ls` - list, typically given with no arguments, prints out the contents of a directory like so:
```
user@computer ~ $ ls
Desktop/ Documents/ Downloads/ example.txt
```

`cd` - change directory, typically given with the argument of a directory. For example:
```
user@computer ~ $ cd Documents
user@computer Documents/ $
```

`mv` - move, typically given with 2 arguments (source and destination), like so:
```
user@computer ~ $ ls
folder/ text.txt
user@computer ~ $ mv text.txt folder/text.txt
user@computer ~ $ ls
folder/
user@computer ~ $ ls folder/
text.txt
```

`rm` remove, typically given with the argument of a file name like so:
```
user@computer ~ $ ls
text.txt
user@computer ~ $ rm text.txt
user@computer ~ $ ls
user@computer ~ $
```

`mkdir` make directory, creates a folder, typically given with the argument of a name, eg:
```
user@computer ~ $ mkdir folder
user@computer ~ $ ls
folder/
```

`touch` create file, usually given with the argument of a name, eg:
```
user@computer ~ $ touch text.txt
user@computer ~ $ ls
touch.txt
```

these are likely to be the commands you use the most. They let you get around and manipulate files, which is 99% of using a computer.

# More advanced stuff
And as with any topic, there's always more advanced things - moving from open chords to barre chords, going from training wheels to riding a bike yourself.
(Arch) Linux is no different. However, we won't be getting into pipes or anything like that yet. Just software that's slightly more complex.

`sudo` - SUperuser DO, allows you to perform tasks that a normal user otherwise cannot do. This is a command that is not used on its own. You would use
`sudo` when you're doing something like using a package manager or messing with files you don't have access to. You can use `sudo` with any command, but
most do not require it - however, for the ones that do, you simply type the command like normal after typing `sudo`.

`pacman` - PACkage MANager, allows you to download applications and tools from the internet in the form of 'packages'. Think of it like the app store, but
in your terminal. Use the argument `-S` to install, `-y` to update repositories (essentially, tell the package manager for new directions to the packages cause sometimes
they change address), `-u` to update packages and `-R` to remove packages. You can also use multiple arguments together. For example, to find updates, download updates and
to update all repositories, you can use the argument `-Syu`.

That's it for this section! Move onto [Getting a basic system setup](setup.md) for more info.
