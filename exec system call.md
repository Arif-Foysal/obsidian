#OperatingSystem 

## What is exec() system call?
When you use `fork()`, a new child process is created — a **copy** of the parent.  
But sometimes you don’t want the child to be a copy…  
👉 You want it to run **another program** instead (e.g., `ls`, `python`, etc.)

That’s where `exec` comes in.
## 🔥 `exec` Replaces the Current Process

- It **does not create a new process**.
- It **replaces the current process image** with a new one.
- If `exec` is successful, the code **after exec() will never run**.


![[Pasted image 20250419221454.png]]


## 🛠️ Common Variants of `exec`

All `exec` functions are part of the **`exec` family** from `<unistd.h>`.  
They differ by how you provide the program name and its arguments.

|Function|Description|
|---|---|
|`execl()`|List of args|
|`execlp()`|List of args, search in `$PATH`|
|`execle()`|List of args + env|
|`execv()`|Vector (array) of args|
|`execvp()`|Vector + search `$PATH`|
|`execve()`|Vector + env (lowest level)|

Example:

```cpp
#include <stdio.h>
#include <unistd.h>

int main() {
    printf("Running ls using exec...\n");
    execl("/bin/ls", "ls", "-l", NULL);  // Replace current process with `ls -l`

    // This line will only run if exec fails
    perror("exec failed");
    return 1;
}
```

**🔍 Explanation**
```
execl(path, arg0, arg1, ..., NULL);
```
- `path`: Full path to the executable (e.g., `/bin/ls`)
- `arg0`: By convention, the **name of the program**    
- Followed by more args, ending with `NULL`

## 🚀 Example Using `execvp` (Search `$PATH`)

```cpp
#include <stdio.h>
#include <unistd.h>

int main() {
    char *args[] = {"ls", "-a", NULL};
    execvp("ls", args);  // Automatically finds `ls` in PATH

    perror("execvp failed");
    return 1;
}
```

## ⚠️ Important Notes

- If `exec` **succeeds**, the current program **never returns** to continue.
    
- If it **fails**, it returns `-1` and sets `errno`.
    
- Often used with `fork()` to create a new process and then `exec` in the child.

## Exec with [[Fork System Call|fork()]]

```cpp
pid_t pid = fork();
if (pid == 0) {
    // Child process
    execlp("ls", "ls", "-l", NULL);
    perror("exec failed");
} else {
    // Parent process
    wait(NULL);
    printf("Child finished.\n");
}
```






