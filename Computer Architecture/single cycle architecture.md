#Computer-Science #Computer-Architecture 

>[!Contents]
>[[single cycle architecture#Single Cycle Datapath|Single Cycle Datapath]]
>

[[High Level Program to MIPS Conversion]]
[[MIPS to Machine Language]]


In a single-cycle CPU, each instruction is executed in one clock cycle. It means the CPU fetches, decodes, executes, and writes back the results of an instruction within a single clock cycle. This approach simplifies the control logic, making it easy to design and understand. However, it can be inefficient for complex instructions or those requiring multiple [[clock cycles]] to complete.

**Pros:**
- Simple and easy to design.
- Predictable execution time for all instructions.

**Cons:**
- Long clock cycle time, which reduces performance for complex instructions.
- Hardware may be underutilized as not all parts are active in every cycle.

![[single-cycle-implementation-01.jpg]]
![[MIPS Processor Implementation#Stages of Instruction Execution]]

# Single Cycle Datapath
