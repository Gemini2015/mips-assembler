Mips Assembler
==============

An assembler for a subset of the MIPS instruction set that I wrote in 2011.

# 迁移到Windows平台
Chris Cheng
2014-5-18

## 编译
==============

### 普通编译:
1. 在VC 6.0新建工程
2. 将 .cpp 和 .h 文件加入到工程里面
3. 编译执行 :  
   编译有可能提示关于 inline 的错误，解决方案:  
   工程 - 设置 - C/C++ - 预处理器定义，增加内容： inline=__inline  
   Project - Setting - C/C++ - Precompiler Definetion, add : inline=__inline

### CMake编译（命令行模式）
1. 确保系统安装了CMake
2. 将本项目clone到本地，假设项目目录为 Path，然后在本地建立一个 Build 文件夹
3. CMD或MINGW Bash 切到 Build 目录下，执行以下命令：  
   cmake -G"Visual Studio 6" Path
4. OK

### CMake编译（GUI模式）
1. 打开CMake GUI程序，选择本项目文件夹地址，和目标Build地址
2. Configure 选择 Visual Studio 6，界面出现红色参数，再点一下Configure，最下面提示 Configure done。
3. Generate。

### 提示
1. GUI界面，若参数出错，可以 File -> Delete Cache

## 说明
- unistd.h 并非是真正的 Unix/Linux 下的 unistd.h 文件



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
