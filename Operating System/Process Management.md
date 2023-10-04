#OperatingSystem #processManagement

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
#windows #process 

**Ref:** https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/taskkill

#### taskkill

Ends one or more tasks or processes. Processes can be ended by process ID or image name. You can use the [tasklist command](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/tasklist) command to determine the process ID (PID) for the process to be ended.
>This command replaces the **kill** tool.

##### Syntax
```
taskkill [/s <computer> [/u [<domain>\]<username> [/p [<password>]]]] {[/fi <filter>] [...] [/pid <processID> | /im <imagename>]} [/f] [/t]
```
##### Parameters
|Parameter|Description|
|---|---|
|/s `<computer>`|Specifies the name or IP address of a remote computer (do not use backslashes). The default is the local computer.|
|/u `<domain>\<username>`|Runs the command with the account permissions of the user who is specified by `<username>` or by `<domain>\<username>`. The **/u** parameter can be specified only if **/s** is also specified. The default is the permissions of the user who is currently logged on to the computer that is issuing the command.|
|/p `<password>`|Specifies the password of the user account that is specified in the **/u** parameter.|
|/fi `<filter>`|Applies a filter to select a set of tasks. You can use more than one filter or use the wildcard character (`*`) to specify all tasks or image names. The valid filters are listed in the **Filter names, operators, and values** section of this article.|
|/pid `<processID>`|Specifies the process ID of the process to be terminated.|
|/im `<imagename>`|Specifies the image name of the process to be terminated. Use the wildcard character (`*`) to specify all image names.|
|/f|Specifies that processes be forcefully ended. This parameter is ignored for remote processes; all remote processes are forcefully ended.|
|/t|Ends the specified process and any child processes started by it.|

##### Filter names, operators, and values
|Filter Name|Valid Operators|Valid Value(s)|
|---|---|---|
|STATUS|eq, ne|`RUNNING \| NOT RESPONDING \| UNKNOWN`|
|IMAGENAME|eq, ne|Image name|
|PID|eq, ne, gt, lt, ge, le|PID value|
|SESSION|eq, ne, gt, lt, ge, le|Session number|
|CPUtime|eq, ne, gt, lt, ge, le|CPU time in the format _HH:MM:SS_, where _MM_ and _SS_ are between 0 and 59 and _HH_ is any unsigned number|
|MEMUSAGE|eq, ne, gt, lt, ge, le|Memory usage in KB|
|USERNAME|eq, ne|Any valid user name (`<user>` or `<domain\user>`)|
|SERVICES|eq, ne|Service name|
|WINDOWTITLE|eq, ne|Window title|
|MODULES|eq, ne|DLL name|


##### Examples

To end the processes with process IDs _1230_, _1241_, and _1253_, type:

```
taskkill /pid 1230 /pid 1241 /pid 1253
```

To forcefully end the process _Notepad.exe_ if it was started by the system, type:

```
taskkill /f /fi "USERNAME eq NT AUTHORITY\SYSTEM" /im notepad.exe
```

To end all processes on the remote computer _Srvmain_ with an image name beginning with _note_, while using the credentials for the user account _Hiropln_, type:

```
taskkill /s srvmain /u maindom\hiropln /p p@ssW23 /fi "IMAGENAME eq note*" /im *
```

To end the process with the process ID _2134_ and any child processes that it started, but only if those processes were started by the Administrator account, type:

```
taskkill /pid 2134 /t /fi "username eq administrator"
```

To end all processes that have a process ID _greater than or equal to 1000_, regardless of their image names, type:

```
taskkill /f /fi "PID ge 1000" /im *
```

## Related links

- [[Windows Command-Line Syntax Key]] 
- [[tasklist command]]
