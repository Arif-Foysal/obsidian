> [!Contents]
> [[C Program to MIPS Conversion]]
> 



MIPS stands for "Microprocessor without Interlocked Pipeline Stages." It is both a specific microprocessor architecture and an [[acronym]] for the company that originally designed it, **MIPS Technologies**.

MIPS is a [[Reduced Instruction Set Computer (RISC)]] architecture, which means it uses a simplified set of instructions compared to Complex Instruction Set Computers (CISC). The architecture was developed in the early 1980s and gained popularity in the embedded systems and workstation markets.

The MIPS architecture has been used in various applications, including consumer electronics, networking equipment, gaming consoles, and even supercomputers. It has been particularly prevalent in the early days of digital signal processing, where its efficient instruction set made it suitable for multimedia applications.

The MIPS architecture features a fixed instruction length of 32 bits and a load/store architecture, which means that arithmetic and logic operations are performed only on data in registers. Memory access is done explicitly through load and store instructions.

MIPS processors have undergone several revisions and updates over the years, with different versions offering various enhancements and improvements in performance, power efficiency, and instruction set extensions.

It's worth noting that MIPS has faced competition from other architectures, such as x86, ARM, and PowerPC, especially in the general-purpose computing space. However, it continues to be used in certain specialized areas where its characteristics are advantageous.

In addition to the hardware architecture, MIPS also refers to the MIPS Technologies company, which was acquired by Imagination Technologies in 2013. MIPS processors and architecture are now developed and licensed by Imagination Technologies, which continues to offer a range of MIPS-based processor cores and development tools to its customers.

## Registers:
A register is a special storage location built into the CPU. The data in the registers can be accessed much faster than data in memory.
- The MIPS architecture provides 32 general purpose registers.
    
- The registers each have a symbolic name (for use in assembly language) as well as a numeric code.
    
- Some of the registers are restricted and have a special purpose.
    
- The following is a list of the registers that can be accessed/used by a user program.

|Register Name|Usage|
|:-:|:-|
|`$zero`|constant 0|
|`$t0 - $t9`|temporary storage (not saved across procedure calls)|
|`$s0 - $s7`|saved temporary storage (saved across procedure calls)|
|`$a0 - $a3`|used to pass first 4 arguments to routines.|
|`$v0 - $v1`|used to return values from functions.|
|`$gp`|global pointer -- points to the static data.|
|`$sp`|stack pointer -- points to the top of the stack.|
|`$fp`|frame pointer -- points to the top of the frame in function calls.|
|`$ra`|stores the return address of a procedure call.|

