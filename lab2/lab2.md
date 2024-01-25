---
title: Lab 2 - FIO
description: Using the provided FIO C library to read and output modified data from stdin, to a file and stdout
---

## Objectives
You will build and refresh the skills needed to complete Assignment 2.

## Development Environment and Stencil Code
* We will use VS Code. If you are using Windows and have issues with
Linux/Docker please check the Windows VS Code (WSL+Docker) Tutorial:
\
https://edstem.org/us/courses/50348/discussion/4152846

* The stencil code is available publicly on Github here:
https://github.com/uri-csc412/csc412-s24-labs

## C programs
You will create two small reusable programs inside the programs folder:

1.  readfile.c

2.  linebreaker.c

\
You will use the library FIO; it is in the stencil code. In assignment
2, you will expand its functions and capabilities. For this lab, you
learn how to compile while using a library located in a different
directory. It contains two files:

1.  fio.h (*this is a header file*)

2.  fio.c

### Input and Output Specifications per Program
The stencil for each program contains a **buffer**. This is a different way
to pass data between programs compared to arguments. Your code will read
data from **stdin**, then you will process or manipulate the data, and put
it in **stdout** as the final step. This will enable you to **pipe** (\|) your
programs together in Bash.

### readfile

Your **readfile** program will read a file from the disk called
**test.text** and put that in stdout. The file **test.text** is located
in the /lab2/programs/ directory. This file contains the string matching
text from lab 1, where Prof. Wallace made some typos.\
\
This program will not compile initially. You will need to learn how to
compile a C program that relies on a C library located in another
directory. After you can successfully compile **readfile** you will need
to modify its code so it can return the full contents of **test.text**.


```
$ ./readfile
Holy smokes, you just coded in C and used Bash, congratulations! How
many new things did you do today?
```

### linebreaker

Your **linebreaker** program will read data from stdin, convert all
spaces to linebreaks, and then output each line separately to stdout. One of the autograder
tests will test the speed of your implementation compared to a baseline.
This will be graded leniently in the lab, but exceeding the assignment's
baseline will be more challenging.\
\
This is an example of compiling and running ./linebreaker, where you must type the
text ```Hello, World!``` and press enter. 

```
$ gcc -o linebreaker linebreaker.c
$ ./linebreaker
Hello, World!
Hello,
World!
```

#### Tips: 
* **Ctrl/Cmd + D** terminates any further input from stdin
* **Ctrl/Cmd + C** terminates the program instantly.

## Bash scripts
You will create two bash scripts in the "programs" directory:

1.  lab2.sh

2.  build.sh

### Input and Output Specifications per Script
Your bash scripts will take no arguments. :)

### build.sh
This bash script will compile all C code in the directory it is run. If
any of these C programs rely on outside libraries, it will include these
in the compilation process. This will be something you will need to
figure out with the lab. It will help you learn about paths, and
hopefully appreciate newer more sophisticated compilation methods in the
future.\
\
For build.sh if there are no C programs in your current directory,
provide this helpful message to the user (use stderr):
\
\
```Oops, we found no C code in the directory: <full_directory_path>```
\
\
To pass the Gradescope autograder, you must figure out in bash how you
get the current directory and store that information in a variable to
include in the above message as <full_directory_path>.

### lab2.sh

This bash script will need to accomplish three basic tasks in this
order:

1.  Call build.sh to compile all c code.

2.  Call your readfile and linebreaker programs and save the result in a
    file called **output.text**.

3.  Call your readfile and linebreaker programs and output the text to
    the terminal.

\
Here is an example usage and output. Note, your **output.text** should also match
this text below.

```
$ ./lab2.sh
Holy
smokes,
you
just
coded
in
C
and
used
Bash,
congratulations!
How
many
new
things
did
you
do
today?
```

#### Tips: 
* **Ctrl/Cmd + D** terminates any further input from stdin
* **Ctrl/Cmd + C** terminates the program instantly.

## What to submit

Zip your folders **programs** and **fio** from inside lab2 to
Gradescope. Your folder **programs** should contain:

1.  build.sh

2.  lab2.sh

3.  linebreaker.c

4.  readfile.c

5.  test.text

\
Your folder **fio** should contain:

1.  fio.c

2.  fio.h

\
All grades for the lab will be using the autograder. Prof. Wallace will
review the labs and provide generalized feedback to the whole class
during class time. Attend class, use these insights to reflect on your
code, and improve for Assignment 2. Congrats on finishing Lab 2! :)
