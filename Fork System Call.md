#OperatingSystem 
## What is Fork [[System Call]]?

In UNIX-like operating systems (like Linux), the **`fork()` system call** is how a process asks the OS to **create a new process**.

When you call `fork()` in your code:
- The **OS creates a new process**, called the **child**.    
- The **original process** (the one that called `fork()`) is called the **parent**.

## 🧠 **What’s Special About fork()?**

Here's the surprising part:

✔ The **child process is almost an exact copy of the parent**.
This means:
- The child gets a **copy of the parent's code, stack, heap, and data**.
- It starts **running at the same place** (right after the `fork()` call).
- But the OS makes sure **they are separate**:
    - They have **different process IDs (PIDs)**.
    - Their memory spaces are **separate**, even if they start as copies.
    - File pointers (like open files) are copied but **independently tracked**.

## 🧪 **What Does fork() Return?**

```cpp
int rc = fork();
```

**Here,**
- For child process, 
	rc = 0;
- For parent proces, 
	rc = `pid of the created child`
- rc < 0, if there is an error executing fork()

#### Fork Example

```cpp
pid_t pid = fork();

if (pid == 0) {
    // This block runs in the child
    printf("I'm the child!\n");
} else {
    // This block runs in the parent
    printf("I'm the parent, and my child has PID %d\n", pid);
}
```

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int main(int argc, char *argv[]) {
    printf("hello world (pid:%d)\n", (int) getpid());

    int rc = fork();

    if (rc < 0) {
        // fork failed; exit
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        // child process
        printf("hello, I am child (pid:%d)\n", (int) getpid());
    } else {
        // parent process
        printf("hello, I am parent of %d (pid:%d)\n", rc, (int) getpid());
    }

    return 0;
}
```

Output:
```
hello world (pid:29146)
hello, I am parent of 29147 (pid:29146)
hello, I am child (pid:29147)
```


### However, 





