<div class="container">
<h1>
Computer Architecture
</h1>
<h2>
Assignment 01
</h2>
<p>
Name: MD. Arif Faysal Nayem
<p>ID: 011201194</p>
<p>Course: Computer Architecture</p>
Section: B
</div>


#### Why there is no `subi` instruction in MIPS?
MIPS does not have a `subi` instruction because we can do the same thing using `addi` with a negative number using 2's complement. 
For example, if we want to subtract 3 from `$t0`, we can use the following code:
```MIPS
addi $t0, $t0, -3
```

#### Why there's no `not` instruction in MIPS?

In the MIPS instruction set architecture, there is no direct `not` instruction because we can perform `not` operation by simply using `nor` with a `$zero` register. For instance:
```MIPS
nor $S0, $t0, $zero
```

#### Why there is no `nori` instruction in MIPS?
Nor immediate is not present in MIPS because we can achieve the NOR immediate operation by using the `NOR` instruction in combination with the `ORI` instruction. For example:
```MIPS
ORI $t0, $S0, immediate
NOR $S1, $t0, $zero
```
