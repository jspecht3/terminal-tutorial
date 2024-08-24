# Terminal Tutorial
This is a quick unix-based (Linux and macOS) terminal tutorial geared towards complete beginners. The goal of this tutorial is to be in-depth, but to give you the tools needed to navigate the terminal competently.

For most things in life, it is best to establish a basic framework and incrementally add new things as time progresses; the shell is no different. For now, this tutorial should be all you need, but this is a very brief introduction and should only be the beginning of your journey.

If you are a complete beginner, you should start at the [Introduction](#introduction) and follow the tutorial on your machine. If you just want a list of the commands, go to the [List of Commands](#list-of-commands). 

The first time a command is used in the tutorial, a ✨ will be placed in front of that command. Important concepts will be marked with a 🔴.

- [List of Commands](#list-of-commands)
- [Introduction](#introduction)
- [Nomenclature](#nomenclature)
- [Opening the Terminal](#opening-the-terminal)
- [Basics](#basics)


## List of Commands
Here, you can find a list of terminal commands and a basic description. You can almost always do `<command> --help` in the terminal for more information.

| Command | Meaning | Description |
| --- | --- | --- |
| pwd | print working directory | prints the directory you are currently located, any command will be executed in this directory |
| cd | change directory | changes the current directory |
| mkdir | make directory | creates a directory with the given name |
| ls | list | lists the files in the current directory |



## Introduction
You may have heard the terms "terminal" and "shell" thrown around, perhaps interchangably. However, there is a difference between the two.

The terminal is probably what you are thinking about when you envision either. The terminal is what you are seeing when you are entering commands, navigating directories (sobriquet for folders), and is strictly a display. Terminals used to be physical (e.g., old IBM machines), but are now almost entirely virtual.

However, the terminal cannot work without the shell, which is the brains of the operation. The shell interprets your keyboard inputs and the decides what the terminal should display.

For most intents and purposes, the terminal and shell can be used interchangably because of their inextricable linkage. However, if you are ever confused as to which is which, the shell can be thought of as the "coding language" and the terminal can be thought of as the "output".



## Nomenclature
When following tutorials and guides, you may run into unknown nomenclature. For now, you can skip this section and reference back whenever some unknown nomenclature is used.

If there is confusing nomenclature used (in this tutorial or not), please open a pull request asking for clarification or [email](jspecht3@illinois.edu) me, so it can added for posterity.


### \<some-text\>
When you see `<some-text>`, the tutorial is telling you to replace the text inside `<>` to whatever is applicable to you.

For example, when ssh-ing (getting the terminal of a different machine displayed onto your machine) into another computer, the general formula is:
```
ssh <user>@<hostname>
```
The `<user>` should be replaced with your username for that server and `<hostname>` should be replaced with the link to the server.


### /path/to/folder
Whenever, you see something like `/path/to/folder`, it means you need to change the path to a the directory path on your machine.

For example, if you see
```
cd /path/to/specific-folder
```
The `specific-folder` is the directory you need to path for. If it was on your desktop, you would change the path to
```
cd ~/Desktop/specific-folder
```
Generally, the folder you are looking for was made earlier in the tutorial.


### $ <command>
`$` is used to denote a terminal command and is usually used when there is a mixture of terminal commands and terminal outputs being displayed.

For example, if we want to have out terminal output "Hello World!", we can do the following:
```
$ echo "Hello World!"
Hello World!
```
In this example, the first line `$ echo "Hello World!"` means you are to use the command `echo` with the argument `"Hello World!"`. The second line `Hello World!` shows the output of the command.

This `$` is different from `$variable`, which uses the value of a variable as an argument.



## Opening the Terminal
Opening the terminal is different on each operating system. Navigate to your platform below:

- [Windows](#windows)
- [Linux](#linux)
- [macOS](#macos)


### Windows
Most likely, you are running a windows machine. Windows is great for almost all practical uses, but terminal usage is not one of them. Generally speaking, Unix-based operating systems (Linux and macOS) are better for scientific applications. For better or worse, Windows is a DOS based operating system, meaning, most scientific applications run better on Linux and macOS than Windows.

Fortunately, there is a way to use a Linux terminal on Windows known as Windows Subsystem for Linux (WSL). This allows you to use Linux commands, applications, etc. on Windows without a virtual machine.

You can find an installation guide [here](https://stackoverflow.com/questions/56765067/how-do-i-get-windows-10-terminal-to-launch-wsl). BE WARNED, when you are creating your Ubuntu user, the password will not be displayed, which is normal whenever you are inputting your password.

Once you have the Linux terminal opened, you should see
```
<user>@<computer-name>:~$
```
which means you have everything set up correctly.


### Linux
There are two main ways to open the terminal on Linux.

First, you can use the hotkey `Ctrl` + `Alt` + `T` to open a new terminal window.

Alternatively, you can use the "Super Key" (generally the Windows key) to open the windows manager, search `terminal`, and hit `enter`.


### macOS
There are two main ways to open the terminal on macOS. (from [Apple](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac))

First, you can clock the Launchpad icon in the Dock, type "Terminal", and click the Terminal icon.

Alternatively, in Finder, you can open the `/Applications/Utilities` directory, and double click Terminal.



## Basics
Once you are successfully in the terminal, you should see something like this:
```
<user>@<hostname>:~$
```
Where `user` and `hostname` will be the respective values on your computer.

This line may look innocuous, but contains quite a bit of information. If we parse the output, we can see two segments seperated by a `:`.
```
# this is the first segment
<user>@<hostname>

# this is the second segment
~$
```

The first segment shows the address and the second segment shows the file path. In the first segment, `user` tells you which user is running the command, `@` tells you that specific user is a member of `hostname`. In the second segment, `~` is the file path to your home directory and `$` denotes that you are a regular user.

### Home Directory
As mentioned before `~` is the file path for your (current user's) home directory. However, `~` is simply an alias for the actual path. To see the real path, we can use ✨`pwd`, which stands for "print working directory."
```
joe@v5:~$ pwd
/home/joe
```
With `pwd` we can see that the real path is `/home/joe`, which is the home of the user `joe`.

🔴 `~` is what is known as an alias for `/home/<user>`, which means, anytime you type `~`, the shell will replace the alias `~` with `/home/<user>` when executing commands on the back-end.


### Navigating the Terminal
In the terminal, it may be hard to know where you are and what directories you can work with. To view all of the files (directories included) in the current working directory we can use ✨`ls`, which is short for "list". (our home directories will not look the same)
```
joe@v5:~$ ls
classes    Documents   miniforge  python_files
cpp_files  Downloads   Pictures   recovery
Desktop    miniconda3  snap
```

Now that we can see all of the available directories, let's make a new one that will be used for this tutorial. Before that, we should create a `projects` directory that will be used for all the different projects. We can create directories with ✨`mkdir`, which is short for "make directory."
```
$ mkdir projects 
```

We created a `projects` directory, but don't take my word for it; run `ls` again and see the directory you made.
```
joe@v5:~$ ls
classes    Documents   miniforge  python_files
cpp_files  Downloads   Pictures   recovery
Desktop    miniconda3  projects   snap
```

With `ls`, we now see the `projects` directory. Next, let's create another directory for this project named `terminal-tutorial` inside of the `projects` directory.

```
$ mkdir projects/terminal-tutorial
$ ls projects
terminal-tutorial
```

We created `terminal-tutorial` without even going into `projects`. We can do this because the Unix shell works with 🔴relative file paths, which means, any command that has a file path as an argument can accept the path of a file not in the current directory. If this does not make sense yet, it will once we investigate the file paths for each folder.

To check the file paths, we will use `pwd`. We will also use ✨`cd`, which stands for "change directory."
```
$ pwd
/home/joe
$ cd projects
$ pwd
/home/joe/projects
```

Once we change the directory, the current working directory, shown by `pwd`, changes aswell. When you enter a command into the terminal, that command by default runs in the current working directory (cwd). When executing a command that accepts a file path as an argument, by default, the shell looks at the working directory and makes an alias with the name `.`. 

## Hidden Files
## Shell Files
