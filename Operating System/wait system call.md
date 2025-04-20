
#OperatingSystem 

When we use [[Fork System Call]], the output becomes non-deterministic. 
By using wait system call, we can allow the parent process to wait for a child process to finish what it has been doing.

>This is how we can make the output deterministic.


## Varients

- **wait(NULL)** -> this waits for a single child. If a parent process has 4 children but it calls wait(NULL) for a single time, then after the completion of **any one child**, the parent process will be able to run.
- **waitpid(int child_id)** -> waits for the child with specified PID. If some other child completes execution before the specified child, then the parent will not be able to run.
- If the parent has 4 children and needs to wait for all the children, then it needs to call wait(NULL) for 4 times.
## Example:

![[Pasted image 20250419214502.png]]

**output:**
![[Pasted image 20250419214726.png]]

With this code, we now know that the child will always print first.
- Why do we know that?
- Well, it might simply run first, as before, and thus print before the parent.
- However, if the parent does happen to run first, it will immediately call wait(); this system call won’t return until the child has run and exited .
- Thus, even when the parent runs first, it politely waits for the child to finish running, then wait() returns, and then the parent prints its message.
