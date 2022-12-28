#### Viewing contents of a file
##### Windows
view the contents of a file 
`cat _file`
View the first 10 line of a file-
`cat _file -Head 10`
 View the last 10 lines of a file-
`cat _file -Tail 10`

View the contents of a file one page at a time (just like the man page)
`more _file`
##### Linux
View the contents of a file,similar to `more` command, but better with vim keybindings and more-
`less _file`

`less` keybindings-
|key |what it does |
|:----:|:----|
|/|searches in the file|
|q|quits to the shell|

Many of the powershell command are Alias of bash commands. To show the original command that gets executed we can use the `Get-Alias` command.
`Get-Alias ls` views the original command of `ls`

There is another type of command called `cmd.exe` that we can use in windows.
`cmd.exe` is old and not as powerful as powershell commands.
|Powershell|Alias|cmd.exe|
|----------|-----|-------|
|Get-Children|ls|dir|
##### Getting help
`Get-Help` is used in #powershell commands like-
`Get-Help ls` 
`/?` is used for other commands such as-
`dir /?`
#### Searching within file
##### Windows
###### Searching using GUI:
By default, windows searches only for indexed properties.
We can change that to `index properties and file contents` by changing the indexing option in control panel > indexing options then selecting the folder we want to change indexing > advanced > file types > 
now change the indexing type

The windows search service should start rebuilding the index. This may take some time.

Done! Try searching using your file explorer.
###### Searching using Command Line
`sls` or Select-String command to find words or other string of characters and files. 
Let's search for the word 'foo' in the file one.txt-
`sls foo one.txt` 
we can also search through through several files in the directory using [[wildcards]]
###### searching for something within directory/filtering
`-Filter` option can be used for this job
ex: Listing all the .exe files in the current directory (including the subdirectory)-
`ls -Recurse -Filter *.exe`

##### Linux
[[Linux For Hackers]]

let's find 'foo' in one.txt -
`grep foo one.txt`
This will output lines that has the string 'foo' in it.
You can use the option `-r` to search within directories.
`grep fruit * -r`

using [[wildcards]] is also allowed
#### Input, Output and Pipeline
###### Windows
Each process in #windows as well as #linux has 3 different streams.
1. stdin (Standard IN)
2. stdout (Standard Out)
3. stderr (Standard Error)

The [redirector operator], `>` allows us change where we want out standard output to go.
|redirector|index|
|----------|-----|
|1>|stdout (**Default**)|
|2>|stderr|

Instead of sending stdout to the screen, we can send stdout to a file.
Ex:
warning: This will overwrite the file if it already exists
`echo hello > hello.txt`
To avoid overwriting and append text to the end of a text file, insted of `>` we can use `>>`

The stdout of `echo hello` is redirected to the file `hello.txt`
###### Sending the output to one command to the input of another command
We can use the pipe `|` operator for this job

Ex:
`cat words.txt | Select-String st`
This will output the lines that has the substring 'st'
We can use output redirection to put our filtered lines into a new file-
`cat words.txt | Select-String st > st_words.txt`

###### Redirecting error messages
we can redirect standard error streams to a file

`rmdir /etc 2> ~/error.txt`

What if we don't care about the error messages and stuff and don't want to put them in a file.

we can redirect standard errors in a `$null`
`rmdir /etc 2> $null`
now our output is filtered out error messages.
##### Linux
Similar to windows, linux has the 3 common I/O streams.
Taking input from a file- we can use the `<` operator-
`cat < file.txt`

There is a special file in linux located in `/dev/null` which is similar to `$null` variable in windows-

`rmdir /etc 2> /dev/null`
Output is filtered from error messages.
###### Piping
Taking the output of one command and redirecting it as stdin to another command
`ls -la | grep bluetooth`
stdout of ls -la will redirected as input of grep command
