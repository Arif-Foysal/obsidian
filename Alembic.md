#python #FastApi #dbms 

## 🛠️ What is Alembic?

**Alembic** is a database migration tool for SQLAlchemy. It helps:

- Create migration scripts when you change your models
- Apply migrations safely
- Rollback migrations if needed

---

## 🧪 How Alembic Works with FastAPI

FastAPI doesn’t come with Alembic built-in, but since it uses SQLAlchemy, you can easily plug it in.

---

## 🚀 Step-by-Step: Use Alembic with FastAPI and SQLite

### ✅ 1. Install Requirements

```bash
pip install alembic sqlalchemy
```

---

### ✅ 2. Project Structure

Let’s use this structure:

```
myapp/
├── app/
│   ├── main.py
│   ├── models.py
│   └── db.py
├── alembic/
│   └── versions/
├── alembic.ini
```

---

### ✅ 3. Define Your Models and Base

**app/db.py**

```python
from sqlalchemy.ext.declarative import declarative_base
Base = declarative_base()
```

**app/models.py**

```python
from sqlalchemy import Column, Integer, String
from app.db import Base

class User(Base):
    __tablename__ = "users"
    id = Column(Integer, primary_key=True, index=True)
    name = Column(String, index=True)
```

---

### ✅ 4. Initialize Alembic

```bash
alembic init alembic
```

This creates:

- `alembic/` (with `env.py`)
- `alembic.ini`

---

### ✅ 5. Configure Alembic

**Edit `alembic.ini`:**

Find this line:

```ini
sqlalchemy.url = sqlite:///./test.db
```

Change it to your real database path, like:

```ini
sqlalchemy.url = sqlite:///./app.db
```

**Edit `alembic/env.py`:**

Import your `Base` and models so Alembic knows what to track.

```python

# Import your models and Base
from app.db import Base
from app import models  # make sure to import all models

config = context.config
fileConfig(config.config_file_name)
target_metadata = Base.metadata
```

---

### ✅ 6. Create Your First Migration

Run:

```bash
alembic revision --autogenerate -m "create users table"
```

Check the script Alembic generated in `alembic/versions/`. It should include code to create the `users` table.

---

### ✅ 7. Apply the Migration

Run:

```bash
alembic upgrade head
```

This creates the database tables according to your migration.

---

## ✅ You’re Done!

Every time you change the models:

1. Update your models in `models.py`
    
2. Run `alembic revision --autogenerate -m "describe change"`
    
3. Run `alembic upgrade head`
    

---

## 🧠 Summary

|Concept|Meaning|
|---|---|
|Migration|Change in database schema|
|Alembic|Tool to manage migrations for SQLAlchemy|
|`revision`|Creates a new migration script|
|`upgrade head`|Applies all new migrations|
|`env.py`|Script that links your models to Alembic|

---

Would you like a **minimal working FastAPI example project** with Alembic setup? I can give you the full code.