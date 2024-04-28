#todo #root 

# Documentation

# Critical Tasks
```dataviewjs
dv.taskList(dv.pages("#A").file.tasks.where(t => !t.completed))
```
# Assignments
```dataviewjs
dv.taskList(dv.pages("#assignment").file.tasks.where(t => !t.completed))
```

# Projects
```dataviewjs
dv.taskList(dv.pages("#project").file.tasks.where(t => !t.completed))
```
# Skills
```dataviewjs
dv.taskList(dv.pages("#skills").file.tasks.where(t => !t.completed))
```

# All Tasks
```dataviewjs
dv.taskList(dv.pages().file.tasks .where(t => !t.completed)) 
```

