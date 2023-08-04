A register is a special storage location built into the CPU. The data in the registers can be accessed much faster than data in memory.
- The MIPS architecture provides 32 general purpose registers.
- The size of a register in the [[MIPS]] architecture is 32 bits.
    
- The registers each have a symbolic name (for use in assembly language) as well as a numeric code.
    
- Some of the registers are restricted and have a special purpose.
    
- The following is a list of the registers that can be accessed/used by a user program.

## Types of Registers in MIPS Architecture

### Register Numbering

| **Register Name** | **Register Number**                                               | **Usage** |
|:-----------------:|:-------------------:|:--------------------------------------------:| 
|       $zero       |          0          |                constant zero                 |           |
|     \$v0-$v1      |         2-3         | values for results and expression evaluation |           |
|     \$a0-$a3      |         4-7         |                  arguments                   |           |
|     \$t0-$t7      |        8-15         |                 temporaries                  |           |
|     \$s0-$s7      |        16-23        |                    saved                     |           |
|     \$t8-$t9      |        24-25        |                    more temporaries                          |           |
|       \$gp        |         28          |                global pointer                              |           |
|       \$sp        |         29          |              stack pointer                                |           |
|       \$fp        |         30          |             frame pointer                                 |           |
|       \$ra        |         31          |          return address                                    |           |



## Building a Register
https://www.youtube.com/watch?v=fpnE6UAfbtU
