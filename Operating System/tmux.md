#linux #shell #programming #productivity

https://tmuxcheatsheet.com/
## About tmux
tmux is a program which runs in a terminal and allows multiple other terminal programs to be run inside it. Each program inside tmux gets its own terminal managed by tmux, which can be accessed from the single terminal where tmux is running - this called multiplexing and tmux is a terminal multiplexer.


## Installation
### ipad

**ish shell**
`apk add tmux`
**ubuntu**
tmux can be found on apt repository

## Usage

**Prefix key**
`ctrl + B`

> waits for command

Detatch from a session-
`ctrl + B` then `D`

Create a new tmux session-
`tmux new -s <session-name>`

Kill a tmux session-
`tmux kill-session -t <session`

**switching between sessions**
**switch to the recent session”
`tmux a`

**list sessions**
`tmux ls`

**switch to a specific session**
`tmux a -t <session-name or session-index>`

Split horizontally (horizontal pane)
`ctrl + B` then `%`

Split vertically (vertical pane)
`ctrl + B` then `”`

### switching between panes

`ctrl + B` then `directional arrows`        //on whichever direction you wanna go

`ctrl + B` then `q` then `<index of the pane>`        
How do you know the indexes?
When you hit 
`ctrl + B` then `q`     //shows indexes of each pane. This is cool
Then pressing the index before the animation disappears will switch to that pane.
### resizing panes
`ctrl + B` then hold `ctrl` then `<directional-arrows>`


