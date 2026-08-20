# Bash to Basics
No matter how complex the topic may be, it's always good practice to briefly talk about the most basic parts of the topic. This guide is no different.
Out of the box, Arch uses bash, which can be proven by running `echo $SHELL` in the terminal. This guide only covers the basics of using the terminal and
using bash, because that's a whole topic in of itself. But, you will learn how to use the terminal.

# What does the text in my terminal mean?
When you first open the terminal, you'll have something that looks similar to this:
```
user@computer ~ $
```
And this may be a little intimidating - but fear not, it is not as scary as it may seem. The 'user' part will be replaced with your username on your computer.
The 'computer' part will be replaced with your host name (what other computers think your computer is called). For example, on my computer, it says `gbx@notwindows`.
The `~` shows what directory (folder) you're in. The `~` represents the home folder, where all the files for your user is kept (like your Documents, Desktop,
Downloads folders). If you changed directory to say the Desktop, the prompt would then become something like `user@computer Desktop $`. Finally, the `$` symbol
represents that you are not using an elevated account. This means you can't do stuff that'll fuck up the computer unless you have permission, basically. If you
logged into a root account (using `su`), the `$` would change to a `#`, meaning that you have elevated permissions and CAN fuck stuff up. Never use the root account
unless you have a damn good reason to, because it is very easy to break things - but more on that later.

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

`rm` - remove, typically given with the argument of a file name like so:
```
user@computer ~ $ ls
text.txt
user@computer ~ $ rm text.txt
user@computer ~ $ ls
user@computer ~ $
```

`mkdir` - make directory, creates a folder, typically given with the argument of a name, eg:
```
user@computer ~ $ mkdir folder
user@computer ~ $ ls
folder/
```

`touch` - create file, usually given with the argument of a name, eg:
```
user@computer ~ $ touch text.txt
user@computer ~ $ ls
text.txt
```

`man` - manual pages (often referred to as manpages), usually given the argument of a commands name, and it shows you how to use it, eg:
```
user@computer ~ $ man examplecommand
NAME
    examplecommand - does something idk
SYNOPSIS
    examplecommand [-FUCKshit]
DESCRIPTION
    I don't know im making this up
user@computer ~ $
```
manpages are usually pretty technical, and it's okay if you don't understand them straight away!! You will as you learn more and more
about Linux, but it's a good habit to get your information from them.

these are likely to be the commands you use the most. They let you get around and manipulate files, which is 99% of using a computer.

# More advanced stuff
And as with any topic, there's always more advanced things - moving from open chords to barre chords, going from training wheels to riding a bike yourself.
(Arch) Linux is no different. However, we won't be getting into pipes or anything like that yet. Just software that's slightly more complex.

`sudo` - SUperuser DO, allows you to perform tasks that a normal user otherwise cannot do. This is a command that is not used on its own. You would use
`sudo` when you're doing something like using a package manager or messing with files you don't have access to. You can use `sudo` with any command, but
most do not require it - however, for the ones that do, you simply type the command like normal after typing `sudo`. When you first use the command, you will
get this pop up:
```
We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:

    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

For security reasons, the password you type will not be visible.
```
It's really important to let this sync in. Sudo is a powerful tool with lots of great usecases - and you should not be scared of it, simply educated on how to use it.
Generally, unless you know exactly what you're doing, don't run a command with sudo, and certainly don't run random commands from the internet with sudo unless you know
exactly what *they* do.

`pacman` - PACkage MANager, allows you to download applications and tools from the internet in the form of 'packages'. Think of it like the app store, but
in your terminal. Uss these arguments to get around:
```-S``` Install Package  
```-y``` Update Package Database (basically like telling the package manager to go find new directions to packages because sometimes they change address), must be used with `-S`  
```-u``` Find what updates can be installed  
```-Syu``` Bring them all together to find, download and install updates  

That's it for this section! Move onto [Getting a basic system setup](setup.md) for more info.
