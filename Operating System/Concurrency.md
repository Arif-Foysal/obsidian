#OperatingSystem 

Concurrency means **multiple tasks running during the same period** — not necessarily at the same instant, but in a way that makes progress simultaneously.

- In a single-core CPU, tasks _take turns_ (via context switching). 
- In a multi-core CPU, tasks can actually run at the same time.

## Mutual Exclusion(Mutex)

When multiple threads access _shared resources_ (like a variable or file), data can become **inconsistent**. Mutual exclusion ensures only **one thread** accesses the critical section at a time.

- This is done using **mutex locks** (or simply _locks_).
    
- Prevents **[[Race Condition]]**.

## **Conditional Variables**
These allow threads to **wait for a condition to become true**. They are used when a thread must pause execution until some condition (like a resource becoming available) is met.

- Paired with a **mutex**.
    
- Allows one thread to wait while another thread signals when it's okay to proceed.
## Wait and Signal Functions
- `.wait()` → causes a thread to sleep until another thread sends a signal.
- `.notify()` or `.notify_all()` → sends signal to wake one or all waiting threads.

```python
import threading

buffer = []
capacity = 5
condition = threading.Condition()

def producer():
    global buffer
    for i in range(10):
        with condition:
            while len(buffer) == capacity:
                condition.wait()  # Wait until there's space
            buffer.append(i)
            print(f"Produced {i}")
            condition.notify()  # Notify the consumer

def consumer():
    global buffer
    for i in range(10):
        with condition:
            while not buffer:
                condition.wait()  # Wait until there's something to consume
            item = buffer.pop(0)
            print(f"Consumed {item}")
            condition.notify()  # Notify the producer

threading.Thread(target=producer).start()
threading.Thread(target=consumer).start()
```

## 🎯 Summary

| Concept                  | Purpose                                                   |
| ------------------------ | --------------------------------------------------------- |
| **Concurrency**          | Multiple tasks progressing together                       |
| **Mutex/Lock**           | Prevents multiple threads from conflicting on shared data |
| **Conditional Variable** | Allows waiting for certain conditions                     |
| **Wait / Signal**        | Thread communication methods using condition variables    |

---

