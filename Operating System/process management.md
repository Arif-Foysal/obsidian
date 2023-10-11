#OperatingSystem #process #processManagement

>[!Contents]
>- [[process management#What is a process|What is a process]]
>- [[process management#Processes in windows|Processes in windows]]
>	- [[process management#Killing a process in windows|Killing a process in windows]]
>- [[process management#Processes in Linux|Processes in Linux]]
## What is a process
A process is a program or a task that is running. A process runs on its own memory space, system resources, and with a unique identifier. 

The way processes are created and stopped differs based on the operating system that you're running.
## Processes in windows
#windows 

When Windows boots up or starts,the first non kernel and user mode that starts as the Session Manager Subsystem or [[smss.exe]]. The smss.exe process is in charge of setting some stuff up for the OS to work. 
It then kicks off the login process called [[windlogon.exe]] appropriately enough. Along with the client server runtime subsystem called [[csrss.exe]], which handles running the Windows GUI and command-line console.

In Windows, each new process that's created needs 
a parent to tell the operating system that a new process needs to be made. The child process inherits some things from its parent,
like variables and settings, which we can collectively refer to as an environment. This gives the child process a pretty good start in life. But after the initial creation step, the child process no longer depends on it's parent process e.g. if we open notepad from powershell command, powershell is the parent process, and notepad is the child. Now if we close powershell, notepad doesn't close. It is now independent from it's parent. 
### Killing a process in windows
![[taskkill]]


## Processes in Linux
#linux 

In Linux, processes have a parent child relationship. This means that every process that you launch comes from another  process. If all processes come from another process, there must be an initial process that started this all, right? Yes, there is. When you start up your computer, the kernel creates a process called init, which has a PID of one. init starts up other processes that we need to get our computer up and running.
## Reading Process Information in Windows

#windows 
![[get-process]]


## Reading Process Information in Linux
