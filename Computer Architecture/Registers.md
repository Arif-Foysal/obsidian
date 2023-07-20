A register is a special storage location built into the CPU. The data in the registers can be accessed much faster than data in memory.
- The MIPS architecture provides 32 general purpose registers.
- The size of a register in the [[MIPS]] architecture is 32 bits.
    
- The registers each have a symbolic name (for use in assembly language) as well as a numeric code.
    
- Some of the registers are restricted and have a special purpose.
    
- The following is a list of the registers that can be accessed/used by a user program.

## Types of Registers

|**Register Name**|**Usage**|
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
