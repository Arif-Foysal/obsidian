>[!Links]
>- [[process management]]

## How does OS runs multiple processes in the same time having limited CPUs?

>By creating an illusion that the computer has endless number of cpus😆

Imagine you have just **one physical CPU**, but you want to run **many programs at the same time** — a web browser, a music player, maybe a code editor.

But here’s the catch: your computer **doesn’t actually run them all at once** — instead, it **rapidly switches** between them.

This is what we mean when we say:

> "**How does the OS provide the illusion of many CPUs?**"

The answer:  
- The OS **virtualizes** the CPU.  
- It runs **one process at a time**, then **pauses** it, **saves its state**, and **runs another**.  
- It keeps doing this so quickly that to you, it **feels like** everything is happening at once.

So, **even one CPU** can **simulate multiple “virtual” CPUs** — by **time-sharing**.

## What is a process?
![[process management#What is a process]]

### Components of a process
Every process has:

- 🧠 **Memory** — includes instructions (code) and data (like variables).
    
- 📦 **Registers** — tiny, fast memory in the CPU holding temporary data.
    
- ⏩ **Program Counter (PC)** — keeps track of **which instruction is next**.
    
- 📍 **Stack Pointer / Frame Pointer** — used to manage the **function call stack**, including parameters, local variables, and return addresses.
    
- 📁 **I/O info** — tracks which **files/devices** the process is using (like open documents or network connections).

## 🧰 **Process API — What the OS Lets You Do with Processes**

The **Process API** is just the **set of operations** the OS gives you for managing processes. It includes:

- **Create**: When you open an app or type a command, the OS **creates a new process**.
    
- **Destroy**: If a process misbehaves or hangs, you can **kill it** (terminate forcefully).
    
- **Wait**: A parent process can **pause and wait** until its child process finishes.
    
- **Miscellaneous Control**: Includes actions like pausing, resuming, changing priority, etc.

>These must be included in any interface of an operating system

## 💾 Loading from program to process

- When you double-click an app or run a script, that program is originally stored on **disk** in a **binary/executable format**.
    
- In early operating systems, this entire program was **loaded into memory all at once** (eager loading).
    
- In modern OSes, we use **lazy loading** — only parts of the program are loaded **when needed** (saves memory).
    
- Once loaded:
    
    - The OS allocates memory for the **stack** (for function calls)
        
    - It also allocates space for the **heap** (for dynamic memory like objects created with `new` or `malloc`)

## 🔁 **Process States — What Stage a Process Is In**

![[Pasted image 20250413180242.png]]

- **Embryo/Starting**:
    - Just after being created.
    - OS is setting up memory for the process and initializing everything.
- **Ready**:
    - The process is **ready to run** but is **waiting its turn** (because the CPU is busy).
    - It’s like being in a queue.
- **Running**:
    - The process is **actively being executed** on the CPU.
- **Blocked**:    
    - The process is **waiting for something** (e.g., reading a file from disk or waiting for input).
    - It can’t run until that I/O operation is done.
- **Zombie/Ending**:
    - The process has **finished running** but still **sits in the system briefly**
    - Why? So its parent process can check **how it exited** (e.g., success or error).
    - Once the parent reads that info, the OS **cleans up** the zombie process.

## 🔁 **What is a Context Switch?**
A **context switch** happens when the **CPU stops running one process** and **starts running another**.

But here’s the trick:  
Every process uses the CPU’s **registers** (like the program counter, stack pointer, etc.) to keep track of where it is and what it's doing.

So when the OS **pauses** a process, it needs to **save all that context** (the values of the registers) somewhere — otherwise, when it comes back, the process would have no idea where it left off.
### 🧠 **How It Works (Step-by-Step)**

1. 👋 A process is **paused** (maybe its time slice ended, or it's waiting on I/O).
2. 💾 The OS **saves the values of all registers** (like PC, SP, general-purpose registers) to memory. This saved info is called the **process's context**.
3. 🧠 The OS picks a **new process** to run.
4. 📥 It **loads that process's saved context** from memory **back into the CPU’s registers**.
5. 🚀 The new process starts running **right where it left off**, as if nothing happened.

This entire switch — saving one context and loading another — is the **context switch**.


![[System Call]]