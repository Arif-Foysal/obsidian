#python 

A **virtual environment** in Python is a self-contained directory that contains a **specific version of Python** and its own **independent set of installed packages**.

### Why do we need virtual environment?
#### 1. **Isolate dependencies**

Different projects may require different versions of the same library. A virtual environment keeps them separate.
> For example:  
> - Project A uses `FastAPI v0.100`, but  
> - Project B needs `FastAPI v0.110`.  
> - Without isolation, they can conflict.
#### 2. **Avoid polluting the system Python**
Installing packages globally can clutter your system and may require admin rights.
#### 3. **Reproducibility**
You can use `requirements.txt` to recreate the exact environment later or on another machine.

### Managing virtual environments
Options to manage virtual environments in python:
- [[venv]]
- [[anaconda]]
- [[uv]]

[[uv]] seems to be more modern and easy to use tool to manage virtual environments in [[Python]]

### Using [[venv]]

Create a virtual environment:
```bash
python3 -m venv env
```

#### Activate virtual environment:
```bash
source env/bin/activate
```

### Deactivate virtual environment
```bash
deactivate
```
