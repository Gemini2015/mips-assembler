cmake_minimum_required (VERSION 2.6)

# project name
project (MIPSAsm)

# Version
set (MIPSAsm_VERSION_MAJOR 1)
set (MIPSAsm_VERSION_MINOR 0)

add_executable(MIPSAsm 
		assembler.cpp
		file_parser.cpp
		)