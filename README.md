ALX Simple Shell Team Project


This is an ALX collaboration project on Shell. We were tasked to create a simple shell that mimics the Bash shell.

Our shell shall be called hsh.

Introduction
This repository is a ALX Holberton School Project. The school project consisted in writing a shell like sh (Bourne Shell) by Stephen Bourne , in C, using a limited number of standard library functions, so instead we used our own function that we rewrited over the past three month Here.

The goal in this project is to make us understand how a shell works.

To single out some core topics which includes;
What is the environment?
The difference between functions and system calls.
How to create processes using execve...
General Requirements


README file, at the root of the folder of the project is mandatory.
Allowed editors: vi, vim, emacs
Compiler;
Ubuntu 20.04 LTS using gcc.
Using the options -Wall -Werror -Wextra -pedantic -std=gnu89
Coding style;
Betty Style.
Shell should not have any memory leaks.
No more than 5 functions per file.
All header files should be include guarded.
How hsh works
Prints a prompt and waits for a command from the user.
Creates a child process in which the command is checked.
Checks for built-ins, aliases in the PATH, and local executable programs.
The child process is replaced by the command, which accepts arguments.
When the command is done, the program returns to the parent process and prints the prompt.
The program is ready to receive a new command.
To exit: press Ctrl-D or enter "exit" (with or without a status).
Works also in non interactive mode.
Usage
In order to run this program,

Clone This Repo;

git clone https://github.com/TosinISOGUN/simple_shell.git

Compile it with;

gcc 4.8.4 -Wall -Werror -Wextra -pedantic *.c -o hsh.

You can then run it by invoking ./hsh in that same directory.

How to use it In order to use this shell, in a terminal, first run the program: prompt$ ./hsh It wil then display a simple prompt and wait for commands. $ A command will be of the type $ command

To invoke hsh, compile all .c files in the repository and run the resulting executable.

hsh can be invoked both interactively and non-interactively. If hsh is invoked with standard input not connected to a terminal, it reads and executes received commands in order.

Example:

$ echo "echo 'hello'" | ./hsh
'hello'
$
If hsh is invoked with standard input connected to a terminal (determined by isatty(3)), an interactive shell is opened. When executing interactively, hsh displays the prompt $ when it is ready to read a command.

Example:

$./hsh
$
Alternatively, if command line arguments are supplied upon invocation, hsh treats the first argument as a file from which to read commands. The supplied file should contain one command per line. hsh runs each of the commands contained in the file in order before exiting.

Example:

$ cat test
echo 'hello'
$ ./hsh test
'hello'
$
Environment
Upon invocation, hsh receives and copies the environment of the parent process in which it was executed. This environment is an array of name-value strings describing variables in the format NAME=VALUE. A few key environmental variables are:

HOME
The home directory of the current user and the default directory argument for the cd builtin command.

$ echo "echo $HOME" | ./hsh
/home/projects
PWD
The current working directory as set by the cd command.

$ echo "echo $PWD" | ./hsh
/home/projects/alx/simple_shell
OLDPWD
The previous working directory as set by the cd command.

$ echo "echo $OLDPWD" | ./hsh
/home/projects/alx/printf
PATH
A colon-separated list of directories in which the shell looks for commands. A null directory name in the path (represented by any of two adjacent colons, an initial colon, or a trailing colon) indicates the current directory.
