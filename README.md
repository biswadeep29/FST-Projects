FLAT Assignment –  FST Projects
This document focuses on the setup and usage for the String Case Conversion and String Reversal projects developed using C++ and the OpenFst library.

Projects Included
1. String Case Conversion
Files: case_converter.cpp, string_case_converter.cpp

Description: Converts all lowercase letters in an input string to uppercase (a → A). This is achieved using a self-looping FST to handle strings of arbitrary length, preserving spaces and digits.

User Input: Accepts a string containing lowercase letters, numbers, and spaces (e.g., hello world 123).

Output: The fully converted uppercase string (e.g., HELLO WORLD 123).

FST Output: case_converter.fst, isyms.sym, osyms.sym (saved in text format for visualization).

How to Run:

g++ case_converter.cpp -o case_converter -lfst
./case_converter

2. String Reversal
File: reverse_user.cpp

Description: Reverses the order of the input string characters (e.g., abcde → edcba). String reversal is a complex FST task, so the implementation generally involves programmatic logic combined with basic FST structure.

User Input: Accepts an input string.

Output: The reversed string.

How to Run:

g++ reverse_user.cpp -o reverse_user -lfst
./reverse_user

Setup & Compilation
1. Install the OpenFst Library
You must install the OpenFst library to compile and run these programs.

On Ubuntu/Debian:

sudo apt-get update
sudo apt-get install libfst-dev

2. Compile and Run
Use g++ to compile each C++ file, linking the OpenFst library with the -lfst flag.

Compile:

g++ <filename>.cpp -o <output_name> -lfst

Run:

./<output_name>

FST Visualization (Drawing the Graph)
To view the generated FST structure (e.g., the case_converter.fst file), you will need the fstdraw and dot utilities (part of Graphviz) installed.

Generating the PDF
Use the following command to generate a PDF file that graphically represents the FST:

fstdraw --isymbols=isyms.sym --osymbols=osyms.sym case_converter.fst | dot -Tpdf > case_converter.pdf

Viewing the PDF (Linux/Ubuntu)
To automatically open the generated PDF file on a typical Linux environment:

xdg-open case_converter.pdf
