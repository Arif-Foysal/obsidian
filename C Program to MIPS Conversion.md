#Computer-Science #uiu #Computer-Architecture 
To command a computer's hardware, you must speak a language. The words of computer's language are called instructions, and it's vocabulary is called an [[instruction set]].

![[mips instrucitons.png]]
# Table

|   |   |   |   |   |
|---|---|---|---|---|
|**Category**|**Instruction**|**Example**|**Meaning**|**Comments**|
|Arithmetic|add|add \$s1,\$s2,$s3|\$s1=\$s2 + $s3|Three register operands|
|subtract|sub \$s1,\$s2,\$s3|$s1 = $s2 – $s3|Three register operands|
|add immediate|addi \$s1,\$s2,20|$s1 = $s2 + 20|Used to add constants|
|Data transfer|load word|lw \$s1,20(\$s2)|\$s1 = Memory[\$s2 + 20]|Word from memory to register|
|store word|sw \$s1,20(\$s2)|Memory[$s2 + 20] = $s1|Word from register to memory|
|load half|lh \$s1,20(\$s2)|\$s1 = Memory[$s2 + 20]|Halfword memory to register|
|load half unsigned|lhu \$s1,20(\$s2)|\$s1 = Memory[$s2 + 20]|Halfword memory to register|
|store half|sh \$s1,20(\$s2)|Memory[$s2 + 20] = $s1|Halfword register to memory|
|load byte|lb \$s1,20(\$s2)|\$s1 = Memory[$s2 + 20]|Byte from memory to register|
|load byte unsigned|lbu \$s1,20(\$s2)|\$s1 = Memory[$s2 + 20]|Byte from memory to register|
|store byte|sb \$s1,20(\$s2)|Memory[$s2 + 20] ****= $s1|Byte from register to memory|
|load linked word|ll \$s1,20(\$s2)|\$s1 = Memory[$s2 + 20]|Load word as 1st half of atomic swap|
|store condition. word|sc \$s1,20(\$s2)|Memory[$s2+20]=$s1;$s1=0 or 1|Store word as 2nd half of atomic swap|
|load upper immed.|lui \$s1,20|$s1 = 20 * 216|Loads constant in upper 16 bits|
|Logical|and|and \$s1,\$s2,\$s3|$s1 = $s2 & $s3|Three reg. operands; bit-by-bit AND|
|or|or \$s1,\$s2,\$s3|$s1 = $s2 \| $s3|Three reg. operands; bit-by-bit OR|
|nor|nor \$s1,\$s2,\$s3|\$s1 = ~ ($s2 \| $s3)|Three reg. operands; bit-by-bit NOR|
|and immediate|andi \$s1,\$s2,20|$s1 = $s2 & 20|Bit-by-bit AND reg with constant|
|or immediate|ori \$s1,\$s2,20|$s1 = $s2 \| 20|Bit-by-bit OR reg with constant|
|shift left logical|sll \$s1,\$s2,10|$s1 = $s2 << 10|Shift left by constant|
|shift right logical|srl \$s1,\$s2,10|$s1 = $s2 >> 10|Shift right by constant|
|Conditional branch|branch on equal|beq \$s1,\$s2,25|if ($s1 == $s2) go toPC + 4 + 100|Equal test; PC-relative branch|
|branch on not equal|bne \$s1,\$s2,25|if ($s1!= $s2) go toPC + 4 + 100|Not equal test; PC-relative|
|set on less than|slt \$s1,\$s2,\$s3|if ($s2 < $s3) $s1 = 1; else $s1 = 0|Compare less than; for beq, bne|
|set on less than unsigned|sltu \$s1,\$s2,\$s3|if ($s2 < $s3) $s1 = 1; else $s1 = 0|Compare less than unsigned|
|set less than immediate|slti \$s1,\$s2,20|if ($s2 < 20) $s1 = 1; else $s1 = 0|Compare less than constant|
|set less than immediate unsigned|sltiu \$s1,\$s2,20|if ($s2 < 20) $s1 = 1; else $s1 = 0|Compare less than constant unsigned|
|Unconditional jump|jump|j 2500|go to 10000|Jump to target address|
|jump register|jr $ra|go to $ra|For switch, procedure return|
|jump and link|jal 2500|$ra = PC + 4; go to 10000|For procedure call|

FIGURE 2.1 MIPS assembly language revealed in this chapter. !is information is also found in Column 1 of the MIPS Reference

Data Card at the front of this book.




# Operations
## Arithmetic's

Every Computer must perform arithmetic operations. The [[MIPS]] assembly language notation-
`add a, b, c` 
	This instructs a computer to add variables `b` and `c` and to put their sum in `a`.
Each MIPS arithmetic instruction performs only one operation and must always have exactly three variables.
> **Translate the following C code to MIPS-**
> ```
> a = b + c;
> d = a - e;
> ```

A MIPS instruction operates on two source operands and places the result in one destination operand. Hence, the two simple statements above compile directly into these two MIPS assembly language instructions:
```
add a, b, c
sub d, a, e
```

>Compile the following C code to MIPS-
>```f = (g + h) – (i + j);
>```

The compiler must break this statement into several assembly instructions, since only one operation is performed per MIPS instruction. the first MIPS instruction calculates the sum of g and h. We must place the result somewhere, so the compiler creates a temporary variable, called t0:
`add t0,g,h # temporary variable t0 contains g + h`
Although the next operation is subtract, we need to calculate the sum of i and j before we can subtract. !us, the second instruction places the sum of i and j in another temporary variable created by the compiler, called t1:
`add t1,i,j # temporary variable t1 contains i + j`
Finally, the subtract instruction subtracts the second sum from the first and places the difference in the variable f, completing the compiled code:
`sub f,t0,t1 # f gets t0 – t1, which is (g + h) – (i + j)`

But the problem is, MIPS has no such thing as Variables. Instead, MIPS use [[Registers]]. One major difference between variables and [[Registers]] is the limited number of registers, typically 32 on current computers, like MIPS. 
So, there is a restriction that three operands of MIPS arithmetic instructions must each be chosen from one of the 32 registers.
[[The reason for limit of 32 resisters]]
It is the [[compilation | compiler]]'s job to associate program variables with registers.

### Compiling a C assignment using Registers
> The assignment statement from our earlier example:
> `f = (g + h) – (i + j);`

Here, the variables `f, g, h, i, j` are assigned to the registers `$S0, $S1, $S2, $S3, $S4` respectively. So, the compiled MIPS code-
```
add $t0, $S1, $S2
add $t2, $S3, $S4
sub $S0, $t0, $t1
```

