#windows #process 

**Ref:** https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/taskkill

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
