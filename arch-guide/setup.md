# Setting up an install
It can be daunting to get into Linux and have basically nothing at the beginning. This page will walk you through installing enough to have
a usable desktop operating system.

# Installing a text editor
There are a lot of text editors for Linux. My favourite is `micro`, but the general gold standard is `nano`. To install an editor, just type:
`sudo pacman -S (your chosen editor)`.
This might well be your first use of sudo - now is a good time to mention, only use it when you need it, or you WILL fuck up your install
eventually.

# Installing an AUR helper
The AUR (Arch User Repository) is where anyone can upload their own applications and tools and whatever for anyone to use - but to install
packages from it is a pain in the arse. So, people have made things called AUR helpers to help with that process. I'll explain how to install
YAY (Yet Another Yoghurt) to install packages from the AUR.

First, install `git`:
`sudo pacman -S git`

Then, clone the YAY repository:
`git clone https://github.com/Jguer/yay.git`

Then, type `cd yay`, before finally running:
`makepkg -si`

and following all the prompts. Yay uses the same syntax as pacman `-S`, `-y`, etc etc, but instead of being typing pacman as your command, you
type yay. Additionally, you do not need to use sudo with yay.

# Installing a web browser
Everyone needs the web in this day and age. Luckily, most major browsers support most major Linux distributions.
You can install: `firefox`, `firefox-esr` (firefox but more stable and slightly older), `chromium`, `brave-bin` (via yay), etc etc with pacman.

# Installing a C compiler
Not everyone needs this right off the bat, but the further you get sucked into Linux, the closer you get to either learning C or compiling
shit from source. The gold standard of C compilers are `GCC` and LLVM's `Clang`, however you can also install `tcc`, `chibicc`, etc etc. You
can install these with pacman.

# Choosing a desktop environment.
You may already have one installed - if you have stuff on your screen and a mouse cursor, you probably do have one. However, the beauty of Linux
is you're not locked into one environment. You can install GNOME, KDE, XFCE, etc etc as mentioned in intro.md. To install a new desktop environment, install
one of the packages: `gnome` + `gnome-extra`, `plasma-desktop` + `plasma-meta`, `xfce4` + `xfce4-goodies`, or whatever desktop you want, just reference
the Arch Wiki.

[Arch Wiki](https://wiki.archlinux.org/title/Main_page)

Go onto [So.. what now?](next.md) for more!
