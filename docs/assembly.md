# Learning Assembly
Learning Linux/Unix assembly with Intel Syntax from pwn.college

https://wiki.osdev.org/CPU_Registers_x86-64#General_Purpose_Registers

## Registers
* RSP - Stores the stack pointer/address. The first thing on the stack is argc, then after that is the pointer/address to the arguments.
* RAX - Register used for choosing syscalls. Put the syscall code into it and then call syscall. Also used for returning a value in function calls.
* RDI - Register used for first argument of a syscall and a function call.

## Register Function Relationship
* rax, rcx, rdx, rsi, rdi, r8, r9, r10, r11 - caller-saved, can be touched by called functions, responsibility of caller to preserve values with push/pop
    * RAX, will almost always be clobbered due to it being used for the return value.
* rbx, rbp, r12, r13, r14, r15 - called-saved, must be untouched by called functions

## Syscalls
https://filippo.io/linux-syscall-table/
* RAX - Used for choosing syscalls.
* RDI - Used for the first argument of a syscall. Is often the "File Descriptor".
* RSI - Used for the second argument of a syscall. Is often the pointer to the data for the syscall to use.
* RDX - Used for the third argument of a syscall. Is often used to store the length used in the syscall.
