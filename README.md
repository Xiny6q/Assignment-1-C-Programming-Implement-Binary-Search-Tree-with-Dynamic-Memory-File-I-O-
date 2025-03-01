Download link :https://programming.engineering/product/assignment-1-c-programming-implement-binary-search-tree-with-dynamic-memory-file-i-o/

# Assignment-1-C-Programming-Implement-Binary-Search-Tree-with-Dynamic-Memory-File-I-O-
Assignment 1: C Programming ( Implement Binary Search Tree with Dynamic Memory &amp; File I/O)
1 Introduction
Basic application programming in C is an essential step down towards the lower levels of computing. This project explores fundamental aspects of getting work done in C:
• Dynamic memory management with malloc()/free()
• Reading data from files in both text and binary format
• Displaying information to the screen
• Reading commands from users in interactive programs
• Dealing with structs and the data structures they can build
The assignment is divided into several problems utilizing many of the above techniques.
• Problem 1 deals with reading data from files into dynamically allocated arrays
• Problem 2 builds a simple display routine which can be used to display the data read using Problem 1 code
• Problem 3 builds a simple binary search tree application
Each problem is fairly independent from the others so may be worked on in any order though to complete Problem 2, code from Problem 1 must be finished.
1.1 Grading Criteria
Credit for this assignment will be given based on two categories.
• Manual Inspection Criteria (~50%): Each problem has a checklist of things that graders will look for. The checklist is in the spec and often contains hints on what to do. Make sure you have a look at these.
• Automated Testing (~50%): After the release of the project, automated tests will be released for each problem later. Instructions on how to use these will be published in the spec so that you can run the tests yourself to see how many points you are getting. Tests require that code compiles and runs according to the descriptions given so make sure you verify that these work.
1.2 Getting Started
Take the following steps to get started
1. Download the code associated with the project linked at the top of the spec. Unzip it and examine some of the provided code.
2. Examine the overview of the files provided listed in the Download and Setup section. This gives brief descriptions of files that already exist and those that you must create.
3. Pick a problem and read. There is a lot of information and many examples provided for each problem. Reading this will help you write the correct code earlier rather than later.
4. Ask questions: if its not clear how to proceed, put up a Piazza post or visit an office hour.
5. Get coding: don’t wait to start for too long as this will greatly increase your stress levels an potentially result in late submissions.
6. Familiarize yourself with the late submission policy for assignments so you are not caught off guard. No submissions will be accepted more than 48 hours after the deadline.
1.3 Makefile
A Makefile is provided as part of this project. Building programs in C is a bit tedious and most folks use build systems of which make is the oldest. The instructions and dependencies to create programs are written in a Makefile which is then interpreted by the make program which will run gcc and other commands to create programs.
Use this Makefile by issuing commands like make deltas_main
> make deltas_main # build problem 1 main program
gcc -Wall -g -c deltas_main.c
gcc -Wall -g -c read_deltas.c
gcc -Wall -g -o deltas_main deltas_main.o read_deltas.o

> make clean # remove all programs/binary object files
rm -f save_deltas deltas_main print_graph_demo graph_file tree_main *.o

> make tree_main # build problem 3 main program
gcc -Wall -g -c tree_main.c
gcc -Wall -g -c tree_funcs.c
gcc -Wall -g -o tree_main tree_main.o tree_funcs.o

> make clean # remove all programs/binary object files
rm -f save_deltas deltas_main print_graph_demo graph_file tree_main *.o

> make # build all programs/objects for the assignment
gcc -Wall -g -c save_deltas.c
gcc -Wall -g -o save_deltas save_deltas.o deltas.h
gcc -Wall -g -c deltas_main.c
gcc -Wall -g -c read_deltas.c
gcc -Wall -g -o deltas_main deltas_main.o read_deltas.o
gcc -Wall -g -c print_graph_demo.c
gcc -Wall -g -c print_graph.c
gcc -Wall -g -o print_graph_demo print_graph_demo.o print_graph.o
gcc -Wall -g -c graph_file.c
gcc -Wall -g -o graph_file graph_file.o print_graph.o read_deltas.o
gcc -Wall -g -c tree_main.c
gcc -Wall -g -c tree_funcs.c
gcc -Wall -g -o tree_main tree_main.o tree_funcs.o
You are not required to understand all that is the Makefile (yet) but it is a very useful tool and may be worth your while to inspect.
1.4 Automated Tests
Automated tests can be downloaded in a zip linked at the top of the spec. These tests are known to work on lab machines only. They may work on other machines/environments but this is not guaranteed or supported.
The provided Makefile allows automated tests to be run via calls like make test-p1 and make test-p2. See the transcript below.
> make test-p1 # run tests for problem 1
gcc -Wall -g -c test_read_deltas.c
gcc -Wall -g -c read_deltas.c
gcc -Wall -g -o test_read_deltas test_read_deltas.o read_deltas.o
===TESTS for P1===
Running binary tests for read_deltas
./test_read_deltas
Test 0 text-5 : read_text_deltas() len= 5 : OK
Test 1 text-128 : read_text_deltas() len= 32 : OK
Test 2 text-one : read_text_deltas() len= 1 : OK
…
========================================
10 / 10 tests passed

> make test-p2 # run tests for problem 2
gcc -Wall -g -c print_graph_demo.c
gcc -Wall -g -c print_graph.c
…
===TESTS for P2===
Testing print_graph via print_graph_demo
./test_print_graph.sh
Output OK
Valgrind OK

Testing graph_file
./test_graph_file.sh
Loading tests… 10 tests loaded
Running 10 tests

RUNNING NORMAL TESTS
TEST 1 text-ten-5 : OK
TEST 2 text-ten-20 : OK
TEST 3 text-21-5 : OK
TEST 4 text-21-12 : OK
TEST 5 int-21-7 : OK
…
=====================================
OVERALL:
10 / 10 Normal correct
10 / 10 Valgrind correct

> make test # run tests for all problems
…
Each problem describes specifically how tests can be run and how credit will be assigned.
Note that in some cases, testing scripts can run single tests at a time which is useful for debugging the test.
While grading, graders will typically download student code on a lab machine and invoke
make test-pX

where X is a problem number. If the Makefile is missing or incomplete or if code does not compile, zero credit will be assigned for the testing grade.
2 Download Code and Setup
Download the code pack linked at the top of the page. Unzip this which will create a project folder. Create new files in this folder. Ultimately you will re-zip this folder to submit it.
File State Notes
Makefile Provided Build file to compile all programs
save_deltas.c Provided Problem 1 sample to create delta files
deltas_main.c Provided Problem 1 main() function
deltas.h Provided Problem 1 header file
read_deltas.c Create Problem 1/2 functions to write

data/short.txt Data Problem 1 data files
data/short.int Data
data/short.4bit Data
data/wave.txt Data
data/wave.int Data
data/wave.4bit Data
print_graph_demo.c Provided Problem 2 demo program
print_graph.c Create Problem 2 function to write
graph_file.c Create Problem 2 main function to write
tree.h Provided Problem 3 header file
tree_funcs.c Create Problem 3 functions to write
tree_main.c Create Problem 3 main function to write

data/stranger-demo.script Data Problem 3 sample input to main program
data/stranger.tree Data Problem 3 sample tree saved to file
data/other.tree Data Problem 3 sample tree saved to file
data/big.tree Data Problem 3 sample big tree saved to file
TESTING
test-data/ Testing Directory in which temporary testing files are written
test_read_deltas.c Testing Problem 1 tests for read_deltas.c
test_print_graph.sh Testing Problem 2 Tests for print_graph_demo
test_graph_file.sh Testing Problem 2 Test script for graph_file
test_graph_file_data.sh Testing Problem 2 Test data for graph_file
test_tree_main.sh Testing Problem 3 Test script for tree_main
test_tree_main_data.sh Testing Problem 3 Test data for tree_main
3 Problem 1: Reading Text and File Data

3.1 Overview: Delta Arrays
This problem centers around a simple task: read integers from a file into a dynamically allocated array. The caveat to this is that the integers in the file are stored in a special format: an initial value followed by deltas or changes from the previous element. An example is below: comments are on the right side
data/short.txt:
20 # start with 20
-2 # subtract 2
-4 # subtract 4
-4 # subtract 4
-3 # subtract 3
-5 # subtract 5
1 # add 1
-2 # subtract 2
4 # add 4
4 # etc…
…
The deltas_main program will read this file and produce the following output
> ./deltas_main text data/short.txt
Reading text format
data_len: 21
# read
0 20
1 18
2 14
3 10
4 7
5 2
6 3
7 1
8 5
9 9
10 5
11 7
12 7
13 5
14 5
15 5
16 7
17 8
18 3
19 7
20 4
Notice the array contents are not exactly what is in the file but rather compute an element by adding on the delta from the file to the previous total, sometimes referred to as a cumulative sum.
Creating Delta files
The data/ directory contains several delta files. These have extensions indicating the format of the data like .txt for textual and .int for binary int data.
The file save_deltas.c is provided and allows you to create your own delta files for testing. It is demonstrated below.
> make save_deltas # builds the save_deltas program
gcc -Wall -g -c save_deltas.c
gcc -Wall -g -o save_deltas save_deltas.o deltas.h

> ./save_deltas # show usage of program
usage: ./save_deltas <format> <filename>
reads input from stdin and outputs in given format to <filename>
if typing numbers in, press Ctrl-D to end input
<format> is one of
text : text ints are in the given filename
int : binary ints are in the given filename
4bit : 4bit binary ints are in the given filename

> ./save_deltas text deltas.txt # save typed deltas in text format in file deltas.txt
10
12
17
15
10
5
-1
3 # press Ctrl-D to end typed input
wrote 8 ints to deltas.txt in text format

> cat deltas.txt # show contents of file deltas.txt on screen
10 2 5 -2 -5 -5 -6 4

> ./save_deltas int binary.int # save typed deltas in binary format in file binary.int
1
5
-1
4
wrote 4 ints to binary.int in int format

> cat binary.int # show binary data: it’s a mess
^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@^@
Read Delta Files: Code to Write
The file deltas_main.c is provided and shows how required functions are called to read data. The main work to be done is in read_deltas.c which will implement several functions for reading data in delta files in different formats.
All code for this problem should be written in read_deltas.c to fill in the definition of the functions described below. As the functions are completed, one can compile the deltas_main.c program and test it on the provided input files.
3.2 Reading Text Integers
In read_deltas.c, define the following function.
int *read_text_deltas(char *fname, int *len);
// Reads integers in text delta format from the file named by fname
// and returns an array of them. The first integer in the file gives
// the starting point and subsequent integers are changes from the
// previous total.
//
// Opens the file with fopen() and scans through its contents using
// fscanf() counting how many text integers exist in it. Then
// allocates an array of appropriate size using malloc(). Uses
// rewind() to go back to the beginning of the file then reads
// integers into the allocated array. Closes the file after reading
// all ints. Returns a pointer to the allocated array.
//
// The argument len is a pointer to an integer which is set to the
// length of the array that is allocated by the function.
//
// If the file cannot be opened with fopen() or if there are no
// integers in the file, sets len to -1 and returns NULL.
Below are some implementation notes explaining some details.
Text Delta Format
As described above, the format of files for this function is text delta which will have the .txt extension. You can look at these files with a text editor. The first number is the starting point and subsequent numbers are changes from the last number. Some examples:
| delta file: | 0 | 2 | 2 | 2 | 2 | 2 | 1 | 2 | 1 | 2 | 1 |
| array value: | 0 | 2 | 4 | 6 | 8 | 10 | 11 | 13 | 14 | 16 | 17 |
| array index: | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |

| delta file: | 20 | -2 | -4 | -4 | -3 | -5 | 1 | -2 | 4 | 4 | -4 |
| array value: | 20 | 18 | 14 | 10 | 7 | 2 | 3 | 1 | 5 | 9 | 5 |
| array index: | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
Note that the contents of delta text files can occur on one line, each on a separate line, or several per line. All numbers will be separated by one or more whitespace characters. Make use of the scanning techniques below to handle this without trouble.
Opening Text Files
Make use of the standard C file I/O function fopen() to open a named file. Do some research to figure out the arguments to this, particularly
• What arguments are passed to fopen() to open a file for reading
• What the function returns on success
• What the function returns on failure which indicates a file could not be opened.
Reading Data from Text Files
Make use of the C function fscanf() which is similar to scanf() to read data. Using a format specifier like %d will skip any whitespace to find the next integer available in the input stream. This allows one to handle data spread across multiple lines easily.
Since the number of integers in the file is not known in advance, use the following two-pass strategy to determine the size of the array required.
1. Use a loop with fscanf() just to count how many integers are in the file. Each time you attempt a read, capture the return value of fscanf(). If the return value is EOF (end of file) then the read failed due to reaching the end of the file.
2. Allocate an array of integers big enough to hold the contents of the file in it. Use malloc() for this.
3. Use the standard C rewind() function to move back to the beginning of the file.
4. Use another loop with fscanf() to read through the file again. This time, each read should store an integer in the array.
Compiling and Running with deltas_main.c
When you have completed this function, you may wish to test it with deltas_main.c. You will likely need to take the following steps:
• Comment out the parts of deltas_main.c which use later functions like read_int_deltas() so there are no undefined references.
• Compile the main program. While you can compile the program with gcc manually as in
> gcc -o deltas_main deltas_main.c read_deltas.c

it is likely that you will want to use the provided Makefile which automatically builds for you as in
> make deltas_main
gcc -Wall -g -c deltas_main.c
gcc -Wall -g -c read_deltas.c
gcc -Wall -g -o deltas_main deltas_main.o read_deltas.o
You may begin examining Makefile as it is an incredibly useful tool for building complex projects.
• Run the program with some data files such as
> ./deltas_main text data/short.txt
Reading text format
data_len: 21
# read
0 20
1 18
2 14
3 10
…
Note that the program needs to be told the format text as the 2nd argument to run properly.
3.3 Reading Binary Integers
In read_deltas.c, define the following function.
int *read_int_deltas(char *fname, int *len);
// Reads integers in binary delta format from the file named by fname
// and returns an array of them. The first integer in the file gives
// the starting point and subsequent integers are changes from the
// previous total.
//
// Integers in the file are in binary format so the size of the file
// in bytes indicates the quantity of integers. Uses the stat() system
// call to determine the file size in bytes which then allows an array
// of appropriate size to be allocated. DOES NOT scan through the file
// to count its size as this is not needed.
//
// Opens the file with fopen() and uses repeated calls to fread() to
// read binary integers into the allocated array. Does delta
// computations as integers are read. Closes the file after reading
// all ints.
//
// The argument len is a pointer to an integer which is set to
// the length of the array that is allocated by the function.
//
// If the file cannot be opened with fopen() or file is smaller than
// the size of 1 int, sets len to -1 and returns NULL.
Binary Delta Format
The file format expected by this file is binary rather than textual so it is likely not possible to examine the data in text format. The data/ directory contains some example files
• data/short.int : 84 bytes : 21 integers
• data/wave.int : 508 bytes : 127 integers
The data in these are identical to the .txt equivalents:
• The first number is the starting point
• Subsequent numbers are changes of the previous number
However, rather than use ASCII characters that are human readable, each integer is stored directly as 4 bytes in the file.
Determining File Size / Array Elements
Since each integer occupies 4 bytes directly in the file, the size of the file corresponds to the number of integers in the file. This allows one to allocate an appropriately sized array based on the file size. This means that no scanning is required to determine how many ints are in the file.
The stat() system call in Unix provides information about a file by filling in values of a struct. The file size in bytes is one such piece of information. Use a calling sequence like the following to determine the binary file size.
struct stat sb; // struct to hold
int result = stat(fname, &sb); // unix system call to determine size of named file
if(result==-1 || sb.st_size < sizeof(int)){ // if something went wrong or bail if file is too small
return NULL;
}
int total_bytes = sb.st_size; // size of file in bytes
Note the use of the struct stat sb, on old convention for declaring a struct as a stack variable. Its memory address is passed to stat() which fills in information. The field st_size is the number of bytes in the file. This can then be used to determine how many ints are in the file (4 bytes per int) and allocate an array with malloc() prior to reading through the file.
Note that this technique only works with binary files. Text files use a variable number of characters/bytes per integer and include formatting characters such as spaces and newlines. This means the number of bytes in the file does not correspond to the number of integers in it.
Reading Binary Data
Files with binary data can be opened identically to the text data but reading requires use of the fread() function. This function differs greatly from fscanf() as it has no format string. Instead, it is meant to read raw bits/bytes from a file into a specified memory address. It is likely that you will use a call similar to the following.
fread(&values[i], sizeof(int), 1, fin);
Address to | bytes for |quantity |file handle
store data | one element |to read |to read from
This call reads a single binary integer into the an array element from an open file handle.
Make sure as you read integers into the array you perform the delta computation of adding on the previous value to the recently read delta.
3.4 OPTIONAL: Reading 4-bit Signed Integers
For those looking for a bit more challenge, optionally implement the following function (pride only: no bonus credit).
int *read_4bit_deltas(char *fname, int *len);
// Reads integers in 4bit delta format from the file named by fname
// and returns an array of them. The first integer in the file gives
// the starting point and subsequent integers are changes from the
// previous total.
//
// Integers in the file are in 4bit format so the size of the file in
// bytes indicates the quantity of integers: 1 4byte integer appears
// at the beginning and subsequently, each byte as two 4bit signed
// integers packed into it. Uses the stat() system call to determine
// the file size in bytes which then allows an array of appropriate
// size to be allocated. DOES NOT scan through the file to count its
// size as this is not needed.
//
// Opens the file with fopen() and uses repeated calls to fread() to
// read binary integers into the allocated array. Does delta
// computations as integers are read. Closes the file after reading
// all ints.
//
// The argument len is a pointer to an integer which is set to
// the length of the array that is allocated by the function.
//
// If the file cannot be opened with fopen() or file is smaller than
// the size of 1 int, sets len to -1 and returns NULL.
4-bit Delta Files
In many applications such as measuring temperature changes every minute, one does not expect large changes. This means a full 32-bit signed integer to represent the change is a waste of space. Instead, a 4-bit signed integer is sufficient to represent deltas between -8 and +7. The 4-bit delta format is as follows.
• The first 4 bytes are a 32 bit integer which is the starting value. This is identical to the previous file formats
• Subsequently, each byte (8 bits) contains TWO 4 bit signed integers which are changes from the previous value.
Like the binary int format above, this format has a direct correspondence of the size of the file to the number of integers
• data/short.int : 21 integers = 4 byte int + (20 ints)/2 ints per byte = 14 bytes.
• data/wave.int : 127 integers = 4 byte int + (126 ints)/2 ints per byte = 67 bytes
This is a significantly compressed size over the sizes of other formats which is useful if space is tight (ex: a remotely located temperatures sensor on top of Mt. Everest).
The trade-off for the space savings is that the 4-bit format requires significantly more skill to decode into a standard array of integer values.
Decoding 4-bit Integers
Note that reading 4-bit ints can be done with fread() as it binary was read in the previous problem. However, one will need to read 1 byte at time and process it to become two integer deltas.
As an example, consider the a file starting in the following way:
Byte 1 Byte 2 Byte 3 Byte 4
0000 0111 0000 0000 0000 0000 0000 0000 // little endian 32 bit int = 7
Byte 5
0011 0101 // delta1: right 4 bits = +3, delta2: left 4 bits = +5
Byte 6
1111 0001 // delta1: right 4 bits = -3, delta2: left 4 bits = +1
Byte 7
0111 1000 // delta1: right 4 bits = -8, delta2: left 4 bits = +7
To handle this file format, one would take the following approach.
• Read the initial value as normal (4 bytes for an int)
• Read 1 byte
• Mask the low 4 bits for the first 4-bit delta
• Shift and mask upper 4 bits for the second 4-bit delta
• Shift both deltas left then right to carry the sign bit (0 positive, 1 negative) across the number.
The following C binary operators are useful for this
int result = 0;
// initializ result: 32 bits all 0

result = x & 0b1111;
// result is bitwise and of x and the binary constant of zeroes with 4
// low-order ones

result = x >> 4;
// result is x shifted 4 bits to the right

result = (x << 28) >> 28;
// result is x shifted left 28, the right 28 to carry its sign bit
// across 32 bits
Combining these bitwise operations will allow one to convert a 4-bit signed integer to a 32-bit signed integer.
3.5 Grading Criteria for P1 GRADING
The following criteria will be checked in read_deltas.c
Weight Criteria
AUTOMATED TESTS make test-p1
10 Provides 10 tests for read_text_deltas() and read_int_deltas()
Compile and run using make test-p1
1 point per test passed

5 Valgrind Memory Checks of test_read_deltas.c
Compile and run using make test-p1
5 points awarded for Valgrind identifying no memory errors
Deductions made based on severity of memory errors identified by Valgrind
MANUAL INSPECTION
10 read_text_deltas()
Clear commenting indicating which part of the count / allocate / read algorithm is being implemented
Clear loop to count number of elements in file prior to allocation
Correctly reading data and checking for end of file with fscanf()
Proper use of malloc() to allocate an appropriately sized array
Proper use of dereference to set the len parameter
File closed prior to return
Clear efforts to check for file open failures or no integers to return NULL

10 read_int_deltas()
Clear commenting indicating which part of the check size / allocate / read algorithm is being implemented
Use of stat() system call to calculate file size
Use of malloc() to allocate correctly sized array
Clear loop using fread() to read binary data into the array
Proper use of dereference to set the len parameter
File closed prior to return
Clear efforts to check for file open failures or no integers to return NULL
4 Problem 2: Graphing Data

4.1 Overview
Prior to advent of graphical displays, computers were mostly operated via text terminals. This meant any graphical displays had to be rendered with character data in a grid. Anyone thinking this format limited the creativity of computer folks is encouraged to open a terminal and run
telnet towel.blinkenlights.nl

which will likely change their tune (allow ~2 hours of viewing time for the full effect).
The purpose of this problem is somewhat more mundane: create a simple plotting routine for the text terminal. This print_graph() function which resides in the print_graph.c file will display an array of numbers on the screen in a graph-like fashion as per the examples below.
> make print_graph_demo # build the provided demo program
gcc -Wall -g -c print_graph_demo.c
gcc -Wall -g -c print_graph.c
gcc -Wall -g -o print_graph_demo print_graph_demo.o print_graph.o

> ./print_graph_demo # run the provided demo program
DEMO DATA 1
===========
length: 22
min: 0
max: 20
range: 20
max_height: 10
units_per_height: 2.00
+—-+—-+—-+—-+-
20 | X
18 | XX
16 | XXX
14 | XXXX
12 | XXXXX
10 | X XXXXXXX
8 | XXX XXXXXXXX
6 | XXXXX XXXXXXXXX
4 | XXXXXXX XXXXXXXXXX
2 | XXXXXXXXXXXXXXXXXXXX
0 |XXXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+-
0 5 10 15 20

DEMO DATA 2
===========
length: 22
min: 0
max: 20
range: 20
max_height: 20
units_per_height: 1.00
+—-+—-+—-+—-+-
20 | X
19 | X
18 | XX
17 | XX
16 | XXX
15 | XXX
14 | XXXX
13 | XXXX
12 | XXXXX
11 | XXXXX
10 | X XXXXXXX
9 | XX XXXXXXX
8 | XXX XXXXXXXX
7 | XXXX XXXXXXXX
6 | XXXXX XXXXXXXXX
5 | XXXXXX XXXXXXXXX
4 | XXXXXXX XXXXXXXXXX
3 | XXXXXXXX XXXXXXXXXX
2 | XXXXXXXXXXXXXXXXXXXX
1 | XXXXXXXXXXXXXXXXXXXXX
0 |XXXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+-
0 5 10 15 20

DEMO DATA 3
===========
length: 50
min: 13
max: 996
range: 983
max_height: 10
units_per_height: 98.30
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
996 | X
897 | X X X X
799 | X X X X X X X X X
701 | XX X X X XXX X XX XXX X X XX
602 | XX X X XX XXX X X XX XXXX XX X XX
504 | XX XXX XX XXX XX X XXX XXXX XX XX X XX
406 | XX X XXX XXXX XXX XX X XXX XXX XXXXXXXXXX X XX
307 | XXX X XXX XXXXXXXXXXX X XXXX XXXXXXXXXXXXXXX X XX
209 | XXX XXXXXXXXXXXXXXXXX XXXXXX XXXXXXXXXXXXXXXXX XX
111 | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
13 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
0 5 10 15 20 25 30 35 40 45

DEMO DATA 4
===========
length: 50
min: 13
max: 996
range: 983
max_height: 18
units_per_height: 54.61
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
996 | X
941 | X X
886 | X X X X
832 | X X X X X X
777 | X X X X XXX X X XXX XX
722 | XX X X X XXX X X XXX XX
668 | XX X X X XXX X XX XXXX X X XX
613 | XX X X XX XXX X XX XXXX XX X XX
559 | XX XXX XX XXX XX X XX XXXX X XX X XX
504 | XX XXX XX XXX XX X XXX XXXX XX XX X XX
449 | XX X XXX XXXX XXX XX X X XXX XXXX XX XX X XX
395 | XXX X XXX XXXX XXX XX X XXX XXX XXXXXXXXXX X XX
340 | XXX X XXX XXXXXXXXXXX X XXX XXXXXXXXXXXXXXX X XX
286 | XXX X XXX XXXXXXXXXXX X XXXX XXXXXXXXXXXXXXX X XX
231 | XXX X XXXXXXXXXXXXXXX XXXXXX XXXXXXXXXXXXXXXXX XX
176 | XXX XXXXXXXXXXXXXXXXX XXXXXX XXXXXXXXXXXXXXXXXXXX
122 | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
67 | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
13 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
0 5 10 15 20 25 30 35 40 45

4.2 A Function For Graphing Data
In the file print_graph.c, write a the following C function.
void print_graph(int *data, int len, int max_height);
// Prints a graph of the values in data which is an array of integers
// that has len elements. The max_height argument is the height in
// character rows that the maximum number data[] should be. A sample
// graph is as follows:
//
// length: 50
// min: 13
// max: 996
// range: 983
// max_height: 10
// units_per_height: 98.30
// +—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
// 996 | X
// 897 | X X X X
// 799 | X X X X X X X X X
// 701 | XX X X X XXX X XX XXX X X XX
// 602 | XX X X XX XXX X X XX XXXX XX X XX
// 504 | XX XXX XX XXX XX X XXX XXXX XX XX X XX
// 406 | XX X XXX XXXX XXX XX X XXX XXX XXXXXXXXXX X XX
// 307 | XXX X XXX XXXXXXXXXXX X XXXX XXXXXXXXXXXXXXX X XX
// 209 | XXX XXXXXXXXXXXXXXXXX XXXXXX XXXXXXXXXXXXXXXXX XX
// 111 | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
// 13 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
// +—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
// 0 5 10 15 20 25 30 35 40 45
Computing Range Statistics
The first step to creating the graph is to compute the minimum and maximum values in the data array. This allows one to compute the range of the data. The max_height argument can then be used to compute how many “units” a data value must have to get an X character at the given heights. All this information is printed prior to the main body of the graph as in the following.
length: 50
min: 13
max: 996
range: 983
max_height: 10
units_per_height: 98.30
^^
2 decimal places
Note that the units_per_height value is a floating point value and it is printed with 2 decimal places of accuracy.
Top and Bottom Axes
The top and bottom axes are simply dashed – lines with a + every 5 steps similar to the following:
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
The left part of the axis is padded with 5 spaces to allow room for vertical axis numbering.
Below the bottom axis, print an index reference every 5 units. This allows particular data elements (data[11] for example) to be located easily. This is easiest to do with printf() and a format specifier like %-5d which will left justify the integers in a field of 5 characters. The bottom axis and numbering should look like
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-
0 5 10 15 20 25 30 35 40 45
^^^^^ ^^^^^
5 spaces 5 chars wide, left justified
Suggestion: To print the axis, use a single loop for the axis line which prints a dash – except on each 5th iteration when it prints a plus + instead.
Main plot Body
There are a variety of ways to create the plate body BUT below is the preferred algorithm which uses integer variables to control the loop. This avoids common problems associated with floating point numbers in loops.
1. Loop from max_height down to 0. Each iteration will draw a “level” of the plot from top to bottom.
2. At the start of each loop, compute the cutoff at the iteration’s level using arithmetic like
min + level * units_per_height

Make sure that to cast this to an integer.
3. Print the vertical axis reference number first so it appears in the left margin. Use a format specifier like %3d | which will print the level number reference right justified in a field of 3 characters followed by a space and a vertical bar.
4. Loop through each element of the data array. If the data element is larger than or equal to the level’s cutoff, print an X. Otherwise, print a space.
5. After printing X/space for each data, print a newline to move down one level.
Your code should use a doubly nested loop to get the printing correct.
Demoing with print_graph_demo.c
A correct implementation of print_graph() should compile against print_graph_demo.c and produce the output shown at the top of this section.
4.3 Main Function for Graphing
The print_graph() function should work seamlessly to print the data array produced by the functions in read_deltas.c. All that remains is a main function to glue these two functions together.
In the file graph_file.c, create a main() function which does the following:
• Accepts 3 command line arguments
1. A format of a file
2. A filename
3. A number which is the maximum height of the graph in characters
• Uses the atoi(str) function to convert the maximum height command line argument from a string to an integer.
• Uses an appropriate function from read_deltas.c to read data from the given file.
• Plots the data using print_graph()
• Frees the data array prior to exiting.
Note that this main() function is VERY similar to the main() in deltas_main.c which means you can lift a lot of code from there to get the job done.
A demonstration of how this program should work is below. follows.
You DO NOT need implement the 4bit file format if you did not do the optional problem on this.
> make graph_file # build using Makefile
gcc -Wall -g -c graph_file.c
gcc -Wall -g -c print_graph.c
gcc -Wall -g -c read_deltas.c
gcc -Wall -g -o graph_file graph_file.o print_graph.o read_deltas.o

> ./graph_file # no arguments gives usage message
usage: graph_file <format> <filename> <height>
<format> is one of
text : text ints are in the given filename
int : binary ints are in the given filename
4bit : 4bit binary ints are in the given filename

> ./graph_file text data/short.txt 5 # graph the text short.txt file, height 5
Reading text format
length: 21
min: 1
max: 20
range: 19
max_height: 5
units_per_height: 3.80
+—-+—-+—-+—-+
20 |X
16 |XX
12 |XXX
8 |XXXX X X
4 |XXXXX XXXXXXXXXX XX
1 |XXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+
0 5 10 15 20

> ./graph_file text data/short.txt 20 # graph the text short.txt file, height 20
Reading text format
length: 21
min: 1
max: 20
range: 19
max_height: 20
units_per_height: 0.95
+—-+—-+—-+—-+
20 |X
19 |X
18 |XX
17 |XX
16 |XX
15 |XX
14 |XXX
13 |XXX
12 |XXX
11 |XXX
10 |XXXX
9 |XXXX X
8 |XXXX X X
7 |XXXXX X XX XX X
6 |XXXXX X XX XX X
5 |XXXXX XXXXXXXXXX X
4 |XXXXX XXXXXXXXXX XX
3 |XXXXX X XXXXXXXXXXXXX
2 |XXXXXXX XXXXXXXXXXXXX
1 |XXXXXXXXXXXXXXXXXXXXX
1 |XXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+
0 5 10 15 20

> ./graph_file int data/short.int 10 # graph the binary short.int file, height 10
Reading binary int format
length: 21
min: 1
max: 20
range: 19
max_height: 10
units_per_height: 1.90
+—-+—-+—-+—-+
20 |X
18 |XX
16 |XX
14 |XXX
12 |XXX
10 |XXXX
8 |XXXX X X
6 |XXXXX X XX XX X
4 |XXXXX XXXXXXXXXX XX
2 |XXXXXXX XXXXXXXXXXXXX
1 |XXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+
0 5 10 15 20

> ./graph_file int data/wave.int 15 # graph the binary wave.int file, heigh 15
Reading binary int format
length: 127
min: -20
max: 20
range: 40
max_height: 15
units_per_height: 2.67
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+-
20 | XXXX XXXX
17 | XXXXXXXXXXXX XXXXXXXXXXXX
14 | XXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXX
12 | XXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXX
9 | XXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXX
6 | XXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXX
4 | XXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXX
1 | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
-1 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX X
-4 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXX
-6 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXX
-9 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXX
-12 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXX
-14 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXX
-17 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX XXXXXXXXXXX
-20 |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+—-+-
0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75 80 85 90 95 100 105 110 115 120 125
4.4 Grading Criteria for P2 GRADING
The test_graph_file.sh script creates outputs in the test-data/ directory such as test-data/actual.txt which is the output on test which may be useful to inspect. Running a single test as in
./test_graph_file.sh 4

ensures that files in the test-data/ directory correspond to the results of that single test.
Weight Criteria
AUTOMATED TESTS make test-p2
5 test_print_graph.sh
Script which checks output of print_graph_demo
Compile and run using make test-p2 OR
Run individually by doing ./test_print_graph.sh
0-4 points assigned based on matching expected output
1 point assigned for avoiding memory problems identified by Valgrind

10 test_graph_file.sh
10 tests for graph_file executable
Compile and run using make test-p2 OR
Run script using ./test_graph_file.sh
1 point per test passed
0-3 point deduction if Valgrind identifies memory problems
NOTE: individual tests can be run by doing
./test_graph_file.sh 4 # runs test 4
MANUAL INSPECTION
5 print_graph.c
Clear commenting indicating what part of the graph is being printed throughout
Block which prints the initial statistics such as min/max/range
Clearly marked blocks for printing top and bottom axis
Clear doubly-nested loop structure to print main graph body
Effective use of printf() with character field widths specified to format numbers padded by spaces.

5 graph_file.c
Clear set of cases which selects the appropriate file format/read function
Both text and binary int formats are handled
Memory allocated by the read function is free()’d in main()
5 Problem 3: Binary Search Trees In C

5.1 Overview
This problem implements a rudimentary binary search tree in C along with a program that uses it. The architecture is similar to a lab problem involving linked lists so reviewing that code can provide some insight. The intent is develop a small application which behaves as the following demo indicates.
> make tree_main # build with Makefile
gcc -Wall -g -c tree_main.c
gcc -Wall -g -c tree_funcs.c
gcc -Wall -g -o tree_main tree_main.o tree_funcs.o
> ./tree_main # run main program
BST Demo
Commands:
print: shows contents of the tree in reverse sorted order
clear: eliminates all elements from the tree
quit: exit the program
add <name>: inserts the given string into the tree, duplicates ignored
find <name>: prints FOUND if the name is in the tree, NOT FOUND otherwise
preorder: prints contents of the tree in pre-order which is how it will be saved
save <file>: writes the contents of the tree in pre-order to the given file
load <file>: clears the current tree and loads the one in the given file
BST> add Lucas # add some data
BST> add Mike
BST> add Dustin
BST> add Will
BST> add El
BST> print # print tree, reverse order, indentation indicates depth/structure
Will # root->right->right
Mike # root->right
Lucas # root
El # root->left->right
Dustin # root->left
BST> preorder # show tree in preorder, root first
Lucas # root
Dustin # root->left
El # root
Mike # root->right
Will # root->right->right
BST> find Mike
FOUND
BST> find Nancy
NOT FOUND
BST> add Nancy # add Nancy
BST> print
Will
Nancy # root->right->right->left
Mike
Lucas
El
Dustin
BST> find Max
NOT FOUND
BST> add Max # add max
BST> print
Will
Nancy
Mike # root->right->left
Max
Lucas
El
Dustin
BST> find Max
FOUND
BST> find Barb
NOT FOUND
BST> add Barb # add Barb
BST> print
Will
Nancy
Mike
Max
Lucas
El
Dustin
Barb # root->left->left

BST> save stranger.tree # save tree into named file
BST> clear # eliminate tree
BST> print # print shows nothing: empty tree
BST> add Demigorgon # add Demigorgon to empty
BST> print
Demigorgon # root
BST> load stranger.tree # clear tree, replace with contents of file
BST> print # tree is restored
Will
Nancy
Mike
Max
Lucas
El
Dustin
Barb
BST> add Jim # add Jim
BST> add Joyce # add Joyce
BST> print # show tree
Will
Nancy
Mike
Max
Lucas # root
Joyce # root->left->right->right->right
Jim # root->left->right->right
El
Dustin
Barb
BST> load stranger.tree # clear and reload from file
BST> print # restored to previous contents
Will
Nancy
Mike
Max
Lucas
El
Dustin
Barb
BST> quit # quit program
5.2 tree_funcs.c: tree functions
Examine the header file tree.h to see the two C structs which will be used to represent trees.
// Type of tree nodes
typedef struct node {
char name[128]; // node data
struct node *left; // left branch, NULL if not present
struct node *right; // right branch, NULL if not present
} node_t;

// Type of tree itself
typedef struct {
node_t *root; // root of tree, NULL if tree empty
int size; // number of nodes in tree
} bst_t;
Standard operations are supported by the tree.
• Adding elements
• Searching for an element
• Clearing the entire tree
• Printing tree in reverse sorted order and pre-order (root first, then children)
• Saving and loading from a file
These are broken down into the following C functions which you will need to implement in tree_funcs.c. Keep in mind that to honor the binary search tree property (left less than / right greater than), you will need to use the return values of strcmp() function calls as string data is present in the tree.
// tree_funcs.c: Provides a small library of functions that operate on

// binary search trees of strings.

void bst_init(bst_t *tree);
// Initialize the given tree to have a null root and have size 0.

int bst_insert(bst_t *tree, char name[]);
// Inserts given name into a binary search tree. Uses an ITERATIVE
// (loopy) approach to insertion which starts a pointer at the root of
// the tree and changes its location until the correct insertion point
// is located. Returns 1 if a new node is created and 0 if a duplicate
// name is found in the tree already in which case the name is not
// added.

int bst_find(bst_t *tree, char name[]);
// Determines whether name is present or not in the tree using binary
// search. Returns 1 if name is present and 0 otherwise. Uses an
// ITERATIVE (loopy) approach which starts a pointer at the root of
// the tree and changes it until the search name is found or
// determined to not be in the tree.

void bst_clear(bst_t *tree);
// Eliminate all nodes in the tree setting its contents empty. Uses
// recursive node_remove_all() function to free memory for all nodes.

void node_remove_all(node_t *cur);
// Recursive helper function which visits all nodes in a tree and
// frees the memory associated with them. This requires a post-order
// traversal: visit left tree, visit right tree, then free the cur
// node.

void bst_print_revorder(bst_t *tree);
// Prints the elements of the tree in reverse order at differing
// levels of indentation which shows all elements and their structure
// in the tree. Visually the tree can be rotated clockwise to see its
// structure.

void node_print_revorder(node_t *cur, int indent);
// Recursive helper function which prints all elements in the tree
// rooted at cur in reverse order: traverses right subtree, prints cur
// node, traverses left tree. Parameter ‘indent’ indicates how far to
// indent (2 spaces per indent level).

void bst_print_preorder(bst_t *tree);
// Print all the data in the tree in pre-order with indentation
// corresponding to the depth of the tree. Makes use of
// node_write_preorder() for this.

void bst_save(bst_t *tree, char *fname);
// Saves the tree by opening the named file, writing the tree to it in
// pre-order with node_write_preorder(), then closing the file.

void node_write_preorder(node_t *cur, FILE *out, int depth);
// Recursive helper function which writes/prints the tree in pre-order
// to the given open file handle. The parameter depth gives how far to
// indent node data, 2 spaces per unit depth. Depth increases by 1 on
// each recursive call. The function prints the cur node data,
// traverses the left tree, then traverses the right tree.

int bst_load(bst_t *tree, char *fname );
// Clears the given tree then loads new elements to it from the
// named. Repeated calls to bst_insert() are used to add strings read
// from the file. If the tree is stored in pre-order in the file, its
// exact structure will be restored. Returns 1 if the tree is loaded
// successfully and 0 if opening the named file fails in which case no
// changes should be made to the tree.

////////////////////////////////////////////////////////////////////////////////
// OLD VERSIONS

5.3 tree_main.c: main function / application
In tree_main.c implement an interactive program which allows users to type commands to manipulate a binary tree.
The provided Makefile should compile the tree program as follows.
> make tree_main # Compile with Makefile
gcc -Wall -g -c tree_main.c
gcc -Wall -g -c tree_funcs.c
gcc -Wall -g -o tree_main tree_main.o tree_funcs.o

> ./tree_main # Run tree_main
Commands:
print: shows contents of the tree in reverse sorted order
clear: eliminates all elements from the tree
quit: exit the program
add <name>: inserts the given string into the tree, duplicates ignored
find <name>: prints FOUND if the name is in the tree, NOT FOUND otherwise
preorder: prints contents of the tree in pre-order which is how it will be saved
save <file>: writes the contents of the tree in pre-order to the given file
load <file>: clears the current tree and loads the one in the given file
BST>
The following sections provide some implementation details.
Read commands, Execute
The basic flow of tree_main.c follows a provided lab exercise code closely.
• Create a tree variable, likely on the stack as a local variable in main()
• Start a loop that terminates when the user exits or there is no more input
• Each time the user enters a string, read it and check for one of the built-in commands
• On identifying the command, potentially read another string if needed (commands like add and find)
• Call an appropriate bst_XXX() function to handle the command
Supported Commands
To indicate to users of the program the supported commands, use the following code to print out the initial option list.
printf(“BST Demo\n”);
printf(“Commands:\n”);
printf(” print: shows contents of the tree in reverse sorted order\n”);
printf(” clear: eliminates all elements from the tree\n”);
printf(” quit: exit the program\n”);
printf(” add <name>: inserts the given string into the tree, duplicates ignored\n”);
printf(” find <name>: prints FOUND if the name is in the tree, NOT FOUND otherwise\n”);
printf(” preorder: prints contents of the tree in pre-order which is how it will be saved\n”);
printf(” save <file>: writes the contents of the tree in pre-order to the given file\n”);
printf(” load <file>: clears the current tree and loads the one in the given file\n”);
Paths to Tree files for Saving and Loading
Saving and loading trees involves writing to files. The names associated with the files must be specified as a path so that if tree files are to be saved or loaded from subdirectories, include this as part of the path. For example, the stranger.tree file is provided in the data/ directory so can be loaded as follows.
> ./tree_main
…
BST> load data/stranger.tree # load the provided tree from a subdirectory
BST> print # show in reverse sorted order
Will
Nancy
Mike
Max
Lucas
El
Dustin
Barb
BST> preorder # show in preorder
Lucas
Dustin
Barb
El
Mike
Max
Will
Nancy
BST> add Demigorgon # add more data
BST> save cur.tree # save in the current directory
BST> clear
BST> print
BST> load cur.tree # load cur.tree from the current directory
BST> print
Will
Nancy
Mike
Max
Lucas
El
Dustin
Demigorgon # added prior to the save
Barb
BST> add Jim # add more data
BST> save data/other.tree # save to a new file in data/ subdir
BST> quit
Command Echoing: -echo option to tree_main
Some users may wish to “script” this the tree program. An example of such a script is in data/stranger-demo.script which looks like a lot of user commands:
add Lucas
add Mike
add Dustin
add Will
add El
print
preorder
find Mike
find Nancy
add Nancy
print
find Max
add Max
print
find Barb
add Barb
print
save stranger.tree
clear
print
add Demigorgon
print
load stranger.tree
preorder
add Jim
add Joyce
print
load stranger.tree
print
quit
This can be fed directly to the program without needing type it using Unix pipes as per the following:
> cat data/tree-demo.script | ./tree_main -echo
Notice the use of a command line argument for tree_main: the -echo option. This is a REQUIRED feature which prints commands typed by users to the screen. To implement this, do the following.
Model the structure of command echoing after what is shown in related Lab work.
• Use a variable in main() to indicate whether command echoing is on or off; set it to off by default
• Check when main() starts whether command line argument 1 is set to -echo in which case turn echoing on. A condition like the following is useful.
if(argc > 1 && strcmp(“-echo”,argv[1])==0) {
• Each command should check for echoing and print the command being run along with any arguments to it. This technique is demonstrated in related lab work.
It will take some work to get the exact placement of echoes correct but will ultimately lead to nice results that involve LITTLE typing like the example below.
> cat data/stranger-demo.script | ./tree_main -echo
BST Demo
Commands:
print: shows contents of the tree in reverse sorted order
clear: eliminates all elements from the tree
quit: exit the program
add <name>: inserts the given string into the tree, duplicates ignored
find <name>: prints FOUND if the name is in the tree, NOT FOUND otherwise
preorder: prints contents of the tree in pre-order which is how it will be saved
save <file>: writes the contents of the tree in pre-order to the given file
load <file>: clears the current tree and loads the one in the given file
BST> add Lucas
BST> add Mike
BST> add Dustin
BST> add Will
BST> add El
BST> print
Will
Mike
Lucas
El
Dustin
BST> preorder
Lucas
Dustin
El
Mike
Will
BST> find Mike
FOUND
BST> find Nancy
NOT FOUND
BST> add Nancy
BST> print
Will
Nancy
Mike
Lucas
El
Dustin
BST> find Max
NOT FOUND
BST> add Max
BST> print
Will
Nancy
Mike
Max
Lucas
El
Dustin
BST> find Barb
NOT FOUND
BST> add Barb
BST> print
Will
Nancy
Mike
Max
Lucas
El
Dustin
Barb
BST> save stranger.tree
BST> clear
BST> print
BST> add Demigorgon
BST> print
Demigorgon
BST> load stranger.tree
BST> preorder
Lucas
Dustin
Barb
El
Mike
Max
Will
Nancy
BST> add Jim
BST> add Joyce
BST> print
Will
Nancy
Mike
Max
Lucas
Joyce
Jim
El
Dustin
Barb
BST> load stranger.tree
BST> print
Will
Nancy
Mike
Max
Lucas
El
Dustin
Barb
BST> quit
>
5.4 Grading Criteria for P3 GRADING
The following criteria will be checked in this problem.
Weight Criteria
AUTOMATED TESTS make test-p3
15 test_tree_main.sh Testing script
15 tests for tree_main executable, exercises functions in tree_funcs.c
Compile and run using make test-p3 OR
Run script using ./test_tree_main.sh
1 point per test passed
NOTE: individual tests can be run by doing
./test_tree_main.sh 4 # runs test 4

5 Full credit if Valgrind in test_tree_main.sh does not find memory problems
Deductions based on severity of memory problems identified
MANUAL INSPECTION
10 tree_funcs.c
Clear commenting indicating intent during functions such as “go left” or “item found”
Clear use of binary search principle: left for less, right for greater, use of string functions for this
Effective use of iteration in insert and find functions
Effective use of recursion in printing and removal functions
Relatively short functions: nothing needs to be too long (40 lines tops)
Correct order of visiting/freeing in node_remove_all()
Use of one general node_write_preorder in both bst_print_preorder() and bst_save()
Tree cleared prior to load in bst_load() to prevent memory leaks
File closed after finished during saving and loading

10 tree_main.c
Comments indicating what high-level command is being implemented in each part of main
Clear structure of main loop, reading commands, selecting actions
Use of string functions to identify which command to execute
Easy to recognize reading of additional arguments for add/find/etc.
Clear efforts to honor -echo option and echo commands
Clear effort to free all memory prior to exit by clearing tree on exit

