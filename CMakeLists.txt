cmake_minimum_required (VERSION 2.6)
project (MIPSAsm)
add_executable(MIPSAsm 
		assembler.cpp
		file_parser.cpp
		file_parser.h
		hash_function.h
		hash_table.h
		tokenizer.h
		unistd.h
		)