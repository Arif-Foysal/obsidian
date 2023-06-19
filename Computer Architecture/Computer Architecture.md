#Computer-Science #Computer-Architecture #UIU

> [!Contents]
> [[assembly-language]]
> [[MIPS]]

Computer Architecture refers to the structure and design principles of a computer system. It encompasses the organization, functionality and implementation of computer hardware and software that work to perform computational tasks.
## How computers executes programming languages

Computers execute programming languages through a process called [[interpretation]] or [[compilation]]. The specific method used depends on the programming language and the implementation of the language.
> It's worth noting that there are hybrid approaches as well, such as just-in-time (JIT) compilation used in languages like Java or C#. In JIT compilation, the code is initially interpreted, but frequently executed parts are dynamically compiled into machine code for improved performance.

The direct conversion of [[high level language]] to [[low level language]] is very costly. So it is much efficient to convert [[high level language]] to [[assembly-language]] and then convert it to machine language.

> **High Level Language --> Assembly Language/Mid Level Language --> Low Level Language**

## Memory
There are basically two types of memory in computers.
- [[Primary Memory]]
- [[Secondary Memory]]

**CPU <--> Primary Memory <--> Secondary Memory**

Here are the key differences of primary and secondary memory-

|                   | Primary Memory (Main Memory) | Secondary Memory                |
|-------------------|-----------------------------|---------------------------------|
| Definition        | Immediate storage directly accessible by the processor | Non-volatile storage for long-term data retention |
| Speed             | Faster data access and retrieval | Slower compared to primary memory |
| Capacity          | Relatively smaller capacity | Significantly larger capacity |
| Types             | RAM (Random Access Memory) and ROM (Read-Only Memory) | HDDs, SSDs, optical discs, magnetic tapes, external storage devices |
| Cost              | More expensive per unit of storage | Less expensive per unit of storage |
| Volatility        | Volatile (Contents are lost when power is turned off) | Non-volatile (Contents are retained even when power is turned off) |
| Persistence       | Does not retain data when power is turned off | Retains data even when power is turned off |

