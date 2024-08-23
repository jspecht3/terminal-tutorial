# Terminal Tutorial
This is a quick unix-based (Linux and macOS) terminal tutorial geared towards complete beginners. This tutorial is not going to be in-depth, but will give you the tools needed to navigate the terminal.

For most things in life, it is best to establish a basic framework and incrementally add new things as time progresses; the shell is no different. For now, this tutorial should be all you need, but this is a very brief introduction and should only be the beginning of your journey.

- [Introduction](#introduction)
- [Nomenclature](#nomenclature)
- [Opening the Terminal](#opening-the-terminal)


## Introduction
You may have heard the terms "terminal" and "shell" thrown around, perhaps interchangably. However, there is a difference between the two.

The terminal is probably what you are thinking about when you envision either. The terminal is what you are seeing when you are entering commands, navigating directories (sobriquet for folders), and is strictly a display. Terminals used to be physical (e.g., old IBM machines), but are now almost entirely virtual.

However, the terminal cannot work without the shell, which is the brains of the operation. The shell interprets your keyboard inputs and the decides what the terminal should display.

For most intents and purposes, the terminal and shell can be used interchangably because of their inextricable linkage. However, if you are ever confused as to which is which, the shell can be thought of as the "coding language" and the terminal can be thought of as the "outputted display".


## Nomenclature
When following tutorials and guides, you may run into unknown nomenclature. For now, you can skip this section and reference back whenever some unknown nomenclature is used.

If there is confusing nomenclature used (in this tutorial or not), please open a pull request asking for clarification or email me, so it can added for posterity.


### Text between Less Than and Greater Than
When you see `<some-text>`, the tutorial is telling you to replace the text inside `<>` to whatever is applicable to you.

For example, when ssh-ing (getting the terminal of a different machine displayed onto your machine) into another computer, the general formula is:
```
ssh <user>@<server-address>
```
The `<user>` should be replaced with your username for that server and `<server-address>` should be replaced with the link to the server.


### /path/to/folder


### $ <command>
`$` is used to denote a terminal command and is usually used when there is a mixture of terminal commands and terminal outputs being displayed.

For example, if we want to have out terminal output "Hello World!", we can do the following:
```
$ echo "Hello World!"
Hello World!
```
In this example, the first line `$ echo "Hello World!"` means you are to use the command `echo` with the argument `"Hello World!"`. The second line `Hello World!` shows the output of the command.


## Opening the Terminal
Opening the terminal is different in each operating system. Navigate to your platform below:

- [Windows](#windows)
- [Linux](#linux)
- [macOS](#macos)

### Windows
Most likely, you are running a windows machine, which is great for almost all applications, but terminal usage is not one of them. Generally speaking, Unix-based operating systems (Linux and macOS) are better for scientific applications. For better or worse, Windows is a DOS based operating system, meaning, most scientific applications run better on Linux and macOS than Windows.

Fortunately, there is a way to use a Linux terminal on Windows known as Windows Subsystem for Linux (WSL). This allows you to use Linux commands, applications, etc. on Windows without a virtual machine.

You can find an installation guide [here](https://stackoverflow.com/questions/56765067/how-do-i-get-windows-10-terminal-to-launch-wsl). BE WARNED, when you are creating your Ubuntu user, the password will not be displayed, which is normal whenever you are inputting your password.

Once you have the Linux terminal opened, you should see
```
<user>@<computer-name>:~$
```
which means you have everything set up correctly.


### Linux


### macOS



## 
