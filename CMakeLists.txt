project(SimpleDOS C CXX)

cmake_minimum_required(VERSION 3.17)

# setup NASM, so that NASM can build a pure binary data out of a single file
set(CMAKE_ASM_NASM_OBJECT_FORMAT bin)
set(CMAKE_ASM_NASM_LINK_EXECUTABLE "cp <OBJECTS> <TARGET>")
enable_language(ASM_NASM)
if(CMAKE_ASM_NASM_COMPILER_LOADED)
    set(CAN_USE_ASSEMBLER TRUE)
endif(CMAKE_ASM_NASM_COMPILER_LOADED)

# boot sector
add_executable(boot boot/boot.asm)
