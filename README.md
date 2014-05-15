Mips Assembler
==============

An assembler for a subset of the MIPS instruction set that I wrote in 2011.

# Migrate to VC platform


## Setup:
1. Create a new project in VC 6.0
2. Add *.c and *.h file into the project
3. Build Execute :  
   When it show errors about "inline", Solution:  
   Project - Setting - C/C++ - Precompiler Definetion, add : inline=__inline

## Tips
- unistd.h is not the real Unix/Linux unistd.h file.
- The last Instruction in the input file should be followed by a "Enter/return" command

> lui $s1,100  
> lui $s2,30  
> add $s3,$s1,$s2 ;press enter, move the cursor to the next line, or your will get the wrong output  
> (cursor is here)  

# How to use
The assembler will take a file written in assembly language as input on the command line and will produce an output file containing the MIPS machine code. The input file should be in ASCII text. Each line in the input assembly file contains either a mnemonic, a section header (such as .data) or a label (jump or branch target. The maximum length of a line is 256 bytes. Section headers such as .data and .text should be in a line by themselves with no other assembly mnemonic. Similarly, branch targets such as loop: will be on a line by themselves with no other assembly mnemonic. The input assembly file should only contain one data section and one text section. The first section in the file will be the text section, followed by the data section.

The assembler supports the following instruction set:
- la
- lw
- sw
- add
- sub
- addi
- or
- and
- ori
- andi
- slt
- slti
- sll
- srl
- beq
- j
- jr
- jal

# Build
    $ ./assembler add.asm add.txt
