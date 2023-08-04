#Computer-Science #Computer-Architecture 

![[mips-machine-lan-formats.png]]
# Types of Instruction in MIPS
3 types of instructions:
1. **R Type**
	add, sub, and, or, nor, sll, srl, slt, jr
2.  **I Type**
	lw, sw, andi, ori, addi, beq, bne
3. **J Type**
	j, jal

## R Type

![[R-Type-01.svg]]
- op: Basic operation of the instruction, traditionally called opcode.
- rs: The first register source operand.
- rt: The second register source operand.
- rd: The register destination operand. It gets the result of the opetaion.
- shamt: Shift amount.
- funct: Function. This field selects the specific varient of the operation in the op field and it sometimes called function code.

## I Type

![[I-Type-01.svg]]

## J Type

![[J-Type-01.svg]]
