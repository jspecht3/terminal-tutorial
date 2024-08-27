# Terminal Tutorial
This is a quick unix-based (Linux and macOS) terminal tutorial geared towards complete beginners. The goal of this tutorial is to be in-depth, but to give you the tools needed to navigate the terminal competently.

For most things in life, it is best to establish a basic framework and incrementally add new things as time progresses; the shell is no different. For now, this tutorial should be all you need, but this is a very brief introduction and should only be the beginning of your journey. 

This tutorial moves fairly quickly and only brushes on each topic, so if you are struggling to remember how to use each command, that is fine. The goal of this tutorial is exposing you to each concept so you understand they exist and can search for them later. Do not worry if you do not remember how to do everything here, but do try to remember that they can be done. The internet is a powerful technology and, as long as you can phrase a question well enough, there is almost assuredly an answer out there.

If you are a complete beginner, you should start at the [Introduction](#introduction) and follow the tutorial on your machine. If you just want a list of the commands and aliases, go to the [List of Commands and Aliases](#list-of-commands-and-aliases). 

The first time a command is used in the tutorial, a ✨ will be placed in front of that command. Important concepts will be marked with a 🔴.

- [List of Commands and Aliases](#list-of-commands-and-aliases)
- [Introduction](#introduction)
- [Nomenclature](#nomenclature)
- [Opening the Terminal](#opening-the-terminal)
- [Basics](#basics)


## Lists of Commands and Aliases
Here, you can find a list of terminal commands and a basic description. You can almost always do `<command> --help` in the terminal for more information.

| Command | Meaning                 | Description                                                                                    |
| ------- | ----------------------- | ---------------------------------------------------------------------------------------------- |
| pwd     | print working directory | prints the directory you are currently located, any command will be executed in this directory |
| cd      | change directory        | changes the current directory                                                                  |
| mkdir   | make directory          | creates a directory with the given name                                                        |
| ls      | list                    | lists the files in the current directory                                                       |

Here, you can find a few aliases.

| Alias | Real Value         |
| ----- | ------------------ |
| /     | root directory     |
| ~     | home directory     |
| .     | working directory  |
| ..    | previous directory |

Here, you can find a few functions.
| Function | Name | Description |
| --- | --- | --- |
| \| | pipe | redirects the output of one command into the next |


## Introduction
You may have heard the terms "terminal" and "shell" thrown around, perhaps interchangably. However, there is a difference between the two.

The terminal is probably what you are thinking about when you envision either. The terminal is what you are seeing when you are entering commands, navigating directories (sobriquet for folders), and is strictly a display. Terminals used to be physical (e.g., old IBM machines), but are now almost entirely virtual.

However, the terminal cannot work without the shell, which is the brains of the operation. The shell interprets your keyboard inputs and the decides what the terminal should display.

For most intents and purposes, the terminal and shell can be used interchangably because of their inextricable linkage. However, if you are ever confused as to which is which, the shell can be thought of as the "coding language" and the terminal can be thought of as the "output".



## Nomenclature
When following tutorials and guides, you may run into unknown nomenclature. For now, you can skip this section and reference back whenever some unknown nomenclature is used.

If there is confusing nomenclature used (in this tutorial or not), please open an issue asking for clarification, make a pull request adding the clarification, or [email](jspecht3@illinois.edu) me, so it can added for posterity.


### \#
A `#` tells you where a comment begins. You can either have comments that take up a whole line or are inline.

For example, if there are two ways to do something, I might let the user know about each of those methods
```
# this is a comment that takes up a whole line

# method 1: this is a description for the first method
$ <command-1>

# method 2: this is a description for the second method
$ <command-2>  # this is an inline comment
```

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

For example, if we want to have out terminal output "Hello, World!", we can do the following:
```
$ echo "Hello, World!"
Hello, World!
```
In this example, the first line `$ echo "Hello, World!"` means you are to use the command `echo` with the argument `"Hello, World!"`. The second line `Hello, World!` shows the output of the command.

This `$` is different from `$variable`, which uses the value of a variable as an argument.


### Command Line > or >>>
The `>` when seen in the command line prompt, the usual text before `$` in the terminal, generally means you are being prompted for text in some way.

For an example, we can use a `for` loop, drop into a sub-shell, and avoid having to use `;` to separate each line of the loop.
```
$ for i in $(seq 1 3)
> do
> echo $i
> done
1
2
3
```

This sub-shell for the `for` loops saves us the trouble of making our for loop commands exceedingly long and look this:
```
$ for i in $(seq 1 3); do echo $i; done
1
2
3
```

Both `for` loops do the same thing, but the sub-shell method is markedly easier. Sub-shells are used to isolate environments from 


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
This section will cover the need-to-knows of terminal usage. This section should be enough to let you competently navigate the terminal.

- [Overview](#overview)
- [Home Directory](#home-directory)
- [Navigating the Terminal](#navigating-the-terminal)
- [File Paths](#file-paths)
- [Manipulating Files](#manipulating-files)

### Overview
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

As is customary, let's get the terminal to display "Hello, World!". We can do this with the command `echo`, which displays the inputted text in the terminal.
```
$ echo "Hello, World!"
Hello, World!
```

We now see "Hello, World!" returned to us. In this case, we do not need to explicitly need the quotation marks around the text, but it is best practice to do so.

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

We created `terminal-tutorial` without even going into `projects`. We can do this because almost every command works with file paths (relative or absolute) as arguments, which will be discussed more shortly.

To check the file paths, we will use `pwd`. We will also use ✨`cd`, which stands for "change directory."
```
$ pwd
/home/joe
$ cd projects
$ pwd
/home/joe/projects
```


### File Paths
Once we change the directory, the current working directory (cwd), shown by `pwd`, changes aswell. 🔴The cwd has a default alias just like the home directory, where `.` is to the cwd as `~` is to the home diretory.

We can test and verify this alias in any directory by checking the difference in `ls`.
```
$ cd ~
$ ls
classes    Documents   miniforge  python_files
cpp_files  Downloads   Pictures   recovery
Desktop    miniconda3  projects   snap
$ ls .
classes    Documents   miniforge  python_files
cpp_files  Downloads   Pictures   recovery
Desktop    miniconda3  projects   snap
```
As we can see, `ls` and an `ls .` return the same output, which is expected as `.` is an alias for the cwd.

Whenever you enter a command without a specified file path, that command runs in the cwd. However, almost every commands accepts file paths as arguments. Passing a file path as an argument will override the default file path used, the cwd. This is very much analogous to python functions that have default parameters; a default parameter is used until you explicitly specify that parameter.

Another way to think about this concept is that passing the file path as an argument executes that command in the directory you specified and not the cwd.

As mentioned before, file paths come in two flavors, relative and absolute. A relative file path uses the cwd as the base and concatenates the file path you passed to the end. An absolute file path starts from the :red_circle: root directory `/` and ends where you specify.

For an example, let's go to our home directory and check the file path.
```
$ cd ~
$ pwd
/home/joe
```
As we can see, the file path starts with a `/` to denote an absolute file path. Your root directory is where system level files are stored: your operating system, permissions, global programs, etc.

Next, let's navigate to the `terminal-tutorial` directory. (Choose one of the two methods)
```
# first method: you can either do multiple commands
$ cd projects
$ cd terminal-tutorial

# second method: or a single command
$ cd projects/terminal-tutorial

# checking the current directory
$ pwd
home/joe/projects/terminal-tutorial
```
We see that from the home directory, changing directories into `terminal-tutorial` concatenates `/projects/terminal-tutorial` to the cwd. The arguments here are known as relative file paths because we are starting from the cwd and not the root directory. All absolute file paths start from the root directory and are indicated by `/`. You can think of your home directory as a your "personal root directory" as almost all commands you need to do are going to be contained here.

Now, let's get back to the home directory. This can be done a few ways, but the novel method will use the alias :red_circle: `..`, which is the relative file path for the previous directory.
```
$ pwd
home/joe/projects/terminal-tutorial

# method 1: using relative file paths and ..
$ cd ../..
$ pwd
/home/joe

# method 2: using absolute file paths
$ cd /home/joe  # you could also use ~
$ pwd
/home/joe
```
As you can see, both absolute and relative file paths can be used to get where you want. However, you need to know your cwd to use relative file paths, while absolute file paths can be used agnostic of your current location.


### Manipulating Files
Now that we understand file paths, lets go back to `terminal-tutorial` and manipulate some files.
```
$ cd /home/<user>/projects/terminal-tutorial
```

Now, let's create a `.txt` file with :sparkles: `touch` and verify it exists.
```
$ touch example.txt
$ ls
example.txt
```

The `touch` command can be used to create files without needing to go into the file with a text editor like vim.

Now, we have an empty text file. We can verify this file is empty with the command :sparkles: `wc`, which is short for "word count", but gives more information about the file than the word count alone.
```
$ wc example.txt
0 0 0 example.txt
```

We see there are four outputs, but what do each of those three numbers mean? If you ever have questions about command usage, outputs, or anything else, there are a few commands/options that display documentation.

The most ubiquitous way to get the information you are looking for is by coupling the :sparkles: `--help` option with whichever command you need. Let's look at this with `wc`.
```
$ wc --help
```

By reading the third line, we can see that the three outputs from before are the newline, word, and byte counts, respectively. We can also see the usage of the command, a description of the command, all the available options for the command, and even a link to full documentation if any questions remain unresolved.

As a quick note, there are other ways to view documentation that are not reliable as `--help`, but you still may find use with them. These commands are :sparkles: `man`, :sparkles: `help`, and :sparkles: `info`. 
```
$ man wc
$ help wc
$ info wc
```
Where `man` is short for "manual" and is usually the most verbose and nicest to look at. As mentioned previously, the tree above commands are not as reliable as the `--help` option. As a matter of fact, `help wc` does not even work, but was included because `help` is a command that generally does work.

The reason the `--help` option is so ubiquitous is because the commands `man`, `help`, and `info` are built in commands that are only compatable with default commands and not even all default commands. When a developer or team of developers is making a command, they always include `--help` as an option for the command because they want other people to be able to use that command.

#### File Outputs
Now that we understand each number from `wc`, let's change them. We will start by opening `example.txt` and entering in the following text (if you do not know how to use a text editor in the terminal, check out this [vim tutorial](https://github.com/jspecht3/vim-tutorial/blob/main/README.md)).
```
This is the first line
and this is the second.

The above line is empty.
```

Let's rerun `wc` and check how the output has now changed.
```
$ wc example.txt
4 15 73 example.txt
```

This output is telling us there are 4 newlines, 15 words, and 73 characters. However, after counting the number of characters, you will see that there are only 69 visible characters (you can trust me instead of counting yourself). This is because the first three lines end with a "hidden character" `\n` and the last line ends with a hidden character `NUL`.

The use of hidden characters is not particularly relevant to the rest of the tutorial, so feel free to skip this paragraph if you do not care. If you do care, it makes perfect sense that there are hidden charcters used when constructing text files. The protocol for these characters is now Unicode, but was historically ASCII. These protocols tell the computer how to convert text input, which is human legible, to binary, which is computer legible. Without the inclusion of hidden characters, your text editor would not know where to start a new line, put a heading, end a file, or so much more. If you are interested in other hidden characters, you can check out the (List of Unicode characters Wikipedia](https://en.wikipedia.org/wiki/List_of_Unicode_characters).

Now that we have some text in `example.txt`, let's create a copy named `copy.txt` with :sparkles: `cp`, which is short for copy.
```
$ cp example.txt copy.txt
$ ls
copy.txt  example.txt
```

The command `copy` takes two arguments. The first argument is the file that is to be copied and the second argument is the name of the copy.

With `copy`, we now have two identical copies of the same file. If we want to verify these files are the same, we can use :sparkles: `diff`, which is short for difference.
```
$ diff example.txt copy.txt
```

`diff` is a command that shows you how and where two files differ and takes two arguments, which are both file names. `diff` uses the first file as the file to compare against. We are asking the shell "How do we change the first file so it matches the second file?".

Running this, we see there is no output from `diff` because the two files are the same. Let's change that! We can append text to a file by using :sparkles: `<<`, which redirects the output from the standard output (terminal display) to another command.

In this case, we will use `echo` and `<<` to add some text to `copy.txt` and observe the change with `diff`.
```
$ echo "This is a new line." >> copy.txt
$ diff example.txt copy.txt
4a5
> This is a new line.
```

By adding the extra line to `copy.txt`, `diff` now gives us an output. With `diff`, we see two outputs. The first output tells us how the files need to be changed in order for each to be the same. In this case, `4a5` means the fourth line of `example.txt` needs to have the fifth line of `copy.txt` added after to have both files be the same. We also see what text is different between the two in the second line of the output.
```
$ diff copy.txt example.txt
5d4
< This is a new line.
```

As we can see, the first output is `5d4`, which now means we have to delete the fifth line from `copy.txt` to make it the same as `example.txt`.

Great! We can see how two files are different, but what if we just want to see the text in a file? Luckily, we do not have to create an empty text file and use `diff`, although that would work. Instead, we can use the command :sparkles: `cat`, which is short for concatenate. Let's see what `cat` does with `example.txt`.
```
$ cat example.txt
This is the first line
and this is the second.

The above line is empty.
```

With `cat`, we can see the contents of a file without needing to open it with a text editor.

It is nice to see the contents of a file, but what if we have a very long file and only want to see the first few or last few lines? Luckily, we do not have to scroll, but can use a new function called "pipe," :sparkles: `|`. The `|` function redirects the output of one function into another, so you can string commands together without intermediate steps.

Let's look at the usage of `|` with the commands ✨ `head` and ✨`tail`, which, by default, show the first and last 10 lines of a file, respectively. We will compare the output of a standard `cat` to a `cat` piped with `head` then `tail`.

Solo `cat`.
```
$ cat example.txt
This is the first line
and this is the second.

The above line is empty.
```

Combination of `cat` and `head`. The `-1` argument for `head` denotes how many lines will be concatenated from the beginning of `example.txt`.
```
$ cat example.txt | head -1
This is the first line
```

Combination of `cat` and `tail`. Ditto from `head`, but from the end of `example.txt`.
```
$ cat example.txt | tail -1
The above line is empty.
```

We can also use a combination of `head` and `tail` to get a specific line from `example.txt`. Let's get the second line of `example.txt` by, first, getting the first two lines and by, second, getting the last line.
```
$ cat example.txt | head -2 | tail -1
and this is the second.
```

Whew... that was pretty dense, but now, you have the requisite knowledge to investigate the basics of files.

#### Moving, Renaming, and Deleting Files
Next, we will learn how to move, rename, and remove files.

First, let's create a text file called `this-is-a-really-long-file-name.txt` in the home directory by speficying the file path where we want the file to be created.
```
$ touch ~/this-is-a-really-long-file-name.txt
```

Whoops! We actually wanted `this-is-a-really-long-file-name.txt` to be in `projects/terminal-tutorial`. Let's move `this-is-a-really-long-file-name.txt` to this directory with ✨ `mv`, which is short for "move".
```
$ cd ~/projects/termninal-tutorial
$ mv ~/this-is-a-really-long-file-name.txt .
```

With `mv`, first, we need to specify the file we want to move and, second, we need to specify the directory we want the file to be moved to. If you remember from before, `.` is an alias for the current directory, so using `.` as an argument in `mv` moves the specified file to your current directory. It should be noted that we can specify any directory as the second argument of `mv`, so do not think we are limited to only the current directory.

Let's now verify `this-is-a-really-long-file-name.txt` is in `terminal-tutorial`.
```
$ ls
copy.txt  example.txt  this-is-a-really-long-file-name.txt
```

Great, `this-is-a-really-long-file-name.txt` is in the directory. However, the filename is quite cumbersome, so let's rename `this-is-a-really-long-file-name.txt` to something more manageable. We can rename files using `mv`; whenever the two arguments of `mv` are in the same directory, the specified file is renamed to the second argument. Let's rename `this-is-a-really-long-file-name.txt` to `shorter-name`, which is far more manageable.
```
$ ls
copy.txt  example.txt  this-is-a-really-long-file-name.txt
$ mv this-is-a-really-long-file-name.txt shorter-name.txt
$ ls
copy.txt  example.txt  shorter-name.txt
```

Now that we have `shorter-name.txt`, let's make a new directory and copy `shorter-name.txt` into it.
```
$ mkdir new-dir
$ cp shorter-name.txt new-dir
```

We can observe the file structure with a ✨ `tree`, which is not default command, but can be installed with `sudo apt install tree` or with a project manager called pixi and the command `pixi global install tree`. From now on, I will also be using `tree` in this tutorial as it is more visually appealing in some cases. If you do not want to install `tree`, you do not have to as it is purely a visual change.

As a quick aside, pixi is a project manager that is an alternative to python environments. Pixi replicates your development environment down to a hash level on machines of almost any platform with minimal user effort. If you are just starting your Unix journey, I would highly recommend starting on pixi as soon as possible. You can find a pixi tutorial [here](https://github.com/jspecht3/pixi-tutorial) 😄.

Getting back to the terminal tutorial, below is the output for `tree` in `terminal-tutorial`.
```
$ tree
.
├── copy.txt
├── example.txt
├── new-dir
│   └── shorter-name.txt
└── shorter-name.txt
```

We see two copies of `shorter-name.txt` with one in the main directory, or `.`, and the other in `new-dir`. Let's now delete the `shorter-name.txt` in `.` with :sparkles: `rm`, which is short for remove.
```
$ rm shorter-name.txt
$ tree
.
├── copy.txt
├── example.txt
└── new-dir
    └── shorter-name.txt
```

Now, there is only a single `shorter-name.txt` in `new-dir`. It is very important to note that `rm` is permenant, so, unless you have it backed up with some sort of version control, any file removed with `rm` is gone forever.

Now that the old `shorter-name.txt` is gone, let's go into `new-dir` and copy `shorter-name.txt` a few times. We can use a 🔴 `for` loop and a command called ✨ `seq` to copy `shorter-name.txt` easily. `seq` is short for sequence and generates a series of number from the first argument to the second argument.
```
$ for i in $(seq 1 10)
> do
> file-name="copy$i.txt"
> touch file-name
> done
```

Let's look at all the copies we have created.
```
$ ls
copy10.txt  copy3.txt  copy6.txt  copy9.txt
copy1.txt   copy4.txt  copy7.txt  shorter-name.txt
copy2.txt   copy5.txt  copy8.txt
```



Next, let's try to remove the directory `new-dir` and see what happens.
```
$ rm new-dir/
rm: cannot remove 'new-dir/': Is a directory
```

We see the `rm` does not work on directories by default. This is generally


## Regular Expressions
## Hidden Files
## Shell Files
