A **race condition** happens when **two or more processes/threads access shared data at the same time**, and the **final outcome depends on the timing** of their execution.

In other words,
>When multiple threads "race" to access or modify shared data, whoever gets there first "wins" — and that can break your program.

### 🧠 Real-World Analogy:

Imagine two people writing on the same whiteboard **without checking** what the other is writing.  
They could **overwrite** each other’s messages or write **incomplete/incorrect data**.

Same thing happens in code when threads/processes don’t coordinate.

```cpp
#include <stdio.h>
#include <pthread.h>

int counter = 0;

void* increment(void* arg) {
    for (int i = 0; i < 1000000; i++) {
        counter++;  // ⚠️ Not thread-safe!
    }
    return NULL;
}

int main() {
    pthread_t t1, t2;
    pthread_create(&t1, NULL, increment, NULL);
    pthread_create(&t2, NULL, increment, NULL);
    pthread_join(t1, NULL);
    pthread_join(t2, NULL);
    printf("Final counter: %d\n", counter);  // Expected: 2,000,000 ❌
    return 0;
}
```

You’d expect `2,000,000` but might get **much less**, due to a race condition on `counter++`.

## 🛡️ How to Fix Race Conditions

### 🔐 Use **Mutual Exclusion (mutex/locks)**

Allow **only one thread** to access shared data at a time.

```cpp
#include <pthread.h>

int counter = 0;
pthread_mutex_t lock = PTHREAD_MUTEX_INITIALIZER;

void* increment(void* arg) {
    for (int i = 0; i < 1000000; i++) {
        pthread_mutex_lock(&lock);
        counter++;
        pthread_mutex_unlock(&lock);
    }
    return NULL;
}
```

| Tool / Technique                                       | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ |
| `mutex`                                                | Mutual exclusion – one thread at a time                |
| `semaphore`                                            | General signaling mechanism                            |
| `atomic` operations                                    | Lock-free thread-safe operations                       |
| `monitor`                                              | Object-oriented version of a lock + condition variable |
| `condition variables`                                  | Used with mutexes for signaling                        |
| Process sync: `wait()` / `semaphores` / `pipe` / `shm` | For inter-process coordination                         |