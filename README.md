# f28hs-2022-23-cwk2-sys

These are the template files for F28HS Coursework 2 for OUC students.
See the coursework specification on Canvas for full details of the
coursework.

Links:
- You can use any machine with an installation of the `gcc` C compiler for running the C code of the game logic
- Template for the C program: [master-mind.c](master-mind.c)
- Template for the ARM Assembler program: [mm-matches.s](mm-matches.s)

## Contents

This folder contains the following CW2 specification template files for the source code and for the report:
- `master-mind.c` ... the main C program for the CW implementation, and most aux fcts
- `mm-matches.s`  ... the matching function, implemented in ARM Assembler
- `lcdBinary.c`   ... the low-level code for hardware interaction with LED, button, and LCD;
                      this should be implemented in inline Assembler; 
- `testm.c`       ... a testing function to test C vs Assembler implementations of the matching function
- `test.sh`       ... a script for unit testing the matching function, using the -u option of the main prg

## Getting started

Complete the functions in `master-mind.c` and in `lcdBinary.c`. Initially, you can implement these as C
functions. However, for the final implementation, the low-level functions for controlling LED, button, and
LCD display should be implemented in inline Assembler (in `lcdBinary.c`). Note that the **matching function**,
for calculating the number of exact and approximate matches also needs to be implemented in ARM Assembler.
The file `mm-matches.s` contains a template this Assembler code.

You can test basic functionality by using the `testm.c` C function and the `test.sh` shell script (see below).

## Building and running the application

You can build the main C program (in `master-mind.c`), and the `testm.c` testing function, by typing
> make all

and run the Master Mind program in debug mode by typing
> make run

and do unit testing on the matching function
> make unit

or alternatively check C vs Assembler version of the matching function
> make test

For the Assembler part, you need to edit the `mm-matches.s` file, compile and test this version on the Raspberry Pi.
See the test input data in the `secret` and `guess` structures at the end of the file, for testing.

After having tested the components separately, integrate both so that the C program (in `master-mind.c`)
calls the ARM Assembler code (in `mm-matches.s`) for the matching function.
For controlling the external devices of LED, LCD and button use inline Assembler code, as discussed in
the matching lecture in the course.

The final version of the code should be submitted through Canvas, together with the report and video.

A test script is available to do unit-testing of the matching function. Run it like this from the command line
> sh ./test.sh

To test whether all tests have been successful you can do
> echo $?

which should print `0`.

## Unit testing

This is an example of doing unit-testing on 2 sequences (C part only):
```
> ./cw2 -u 121 313
0 exact matches
1 approximate matches
```

The general format for the command line is as follows (see template code in `master-mind.c` for processing command line options):
```
./cw2 [-v] [-d] [-s] <secret sequence> [-u <sequence1> <sequence2>]
```
# Coursework 2 Mastermind in C and Assembler
# WeChat: cstutorcs

# QQ: 749389476

# Email: tutorcs@163.com

# Computer Science Tutor

# Programming Help

# Assignment Project Exam Help
