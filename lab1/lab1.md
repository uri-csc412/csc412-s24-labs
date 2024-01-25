---
title: Lab 1 - Bash and C Refresher
description: Creating and running two simple Bash and C scripts with arguments
---


## Objectives

You will build and refresh the skills needed to complete Assignment 1.

## Development Environment and Stencil Code
* We will use VS Code. If you are using Windows and have issues with
Linux/Docker please check the Windows VS Code (WSL+Docker) Tutorial:
\
https://edstem.org/us/courses/50348/discussion/4152846

* The stencil code is available publicly on Github here:
https://github.com/uri-csc412/csc412-s24-labs

## C program

### Input Specification
Your C program, **lab1.c** will take in an arbitrary sequence of integers as an input.

### Output Specification
Your program will print all of the integer arguments.

### Example
```bash
$ gcc -Wall lab1.c -o lab1
$ ./lab1 3
3
$ gcc -Wall lab1.c -o lab1
$ ./lab1 3 4 5
3
4
5
```

## Bash Script

### Input Specification
Your bash script, **lab1.sh** will take two or more arguments: a filename containing
your C program's source code and a sequence of integers.

### Output Specification
Your bash script will compile the C source code, given its filename, to **\"lab1\"** (an executable file) and then execute
the compiled program with the integer(s) as an argument.

### Example
If you run the script as ```$ ./lab1.sh lab1.c 4```, your bash script
will:

1.  Compile **lab1.c** to **lab1**

2.  Execute **./lab1 4**

Here is an example of what executing the bash script and its outputs should look like:

```bash
$ ./lab1.sh lab1.c 4
4
$ ./lab1.sh lab1.c 5 6 7
5
6
7
```

## Error handling
None. Assume the user passes correct arguments for each part of the
program. Error checking will be included in the main assignment.

## What to submit
Submit your **lab1.c** and **lab1.sh** files as a zip file to
Gradescope. 

Hint: your zip file should only contain the files
**lab1.c** and **lab1.sh**. Be sure not to zip the directory that they're in, but the files themselves should be zipped together.
