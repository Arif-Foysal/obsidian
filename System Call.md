#OperatingSystem 


[[Fork System Call]]
[[wait system call]]
[[exec system call]]


## What is a system call?

****A system call**** is a programmatic way in which a computer program requests a service from the [[kernel]] of the operating system it is executed on. A system call is a way for programs to ****interact with the operating system****. A computer program makes a system call when it requests the operating system’s kernel. System call ****provides**** the services of the operating system to the user programs via the Application Program Interface(API). System calls are the only entry points into the kernel system and are executed in kernel mode.
![[Screenshot 2025-03-09 at 11.29.01 PM.png]]


![[Fork System Call]]
![[wait system call]]

## Practice Problems

**1. How does your shell execute commands?**
Ans:

|Step|What Happens|
|---|---|
|1. Read input|Shell reads the command|
|2. Parse input|Break into command + args|
|3. Fork|Create a child process|
|4. Exec|Child replaces itself with the command|
|5. Wait|Parent waits for command to finish|
|6. Loop|Go back to prompt|

