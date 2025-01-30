cmake_minimum_required(VERSION 3.10)
project(CO-Lab-Framework C ASM)

set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_C_COMPILER clang)
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_FLAGS "-g -gdwarf-4 -fPIE -Wall -O0 -fsanitize=address -fno-omit-frame-pointer")
set(CMAKE_EXE_LINKER_FLAGS "-g -fsanitize=address -fno-omit-frame-pointer")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../)
# Your programs will run as standalone executables
add_compile_definitions(STANDALONE)

# Targets
add_executable(a1 a1-inout/a1-inout.S)
add_executable(a2 a2-factorial/a2-fac.S)
add_executable(a3a-iter
        a3a-fibonacci-calculator/a3a-fib-main.S
        a3a-fibonacci-calculator/a3a-fib-iter.S
)
add_executable(a3a-rec
        a3a-fibonacci-calculator/a3a-fib-main.S
        a3a-fibonacci-calculator/a3a-fib-rec.S
)
add_executable(a3b a3b-fibonacci-repl/a3b-fib-repl.S)
add_executable(a4
        a4-diff/a4-diff-main.c
        a4-diff/a4-diff.S
)
add_executable(a5 a5-printf/a5-printf.S)

# Clean build
#set_directory_properties(PROPERTIES ADDITIONAL_CLEAN_FILES ${CMAKE_RUNTIME_OUTPUT_DIRECTORY})