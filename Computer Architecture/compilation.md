- Compiled Languages: Compiled languages like C, C++, or Java follow a different approach:
    
    - The source code is written in the programming language and saved in a file, often with a specific file extension (e.g., .c, .cpp, .java).
    - A separate program called a compiler is used to process the source code. The compiler reads the entire source code and translates it into [[assembly-language]].
    - The assembly language code is passed through an [[assembler]], which translates the assembly instructions into machine code. The assembler converts the mnemonic instructions into the binary representation of those instructions understood by the target processor.
    - The output of the assembler is object code, which consists of machine code instructions and data. Object code may be in a relocatable format, allowing it to be linked with other object code files and libraries. The linker combines and resolves references between different object code files, producing an executable file or a shared library.
    - The resulting binary contains the translated machine instructions specific to the target computer architecture.
    - When the executable file is run, the operating system loads it into memory and directly executes the machine instructions.
    
    In compiled languages, the compilation process is performed ahead of time, allowing for faster execution. The compiled binary is usually portable across systems with the same architecture, but may require recompilation for different architectures.
