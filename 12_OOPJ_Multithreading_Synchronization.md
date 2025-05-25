# 12. Multithreading & Synchronization

---

## What is Multithreading?

- **Definition:** A process of executing multiple threads simultaneously for maximum CPU utilization.
- **Purpose:** Efficient use of CPU, enables concurrent execution of tasks (e.g., GUI responsiveness, background processing).

---

## Creating Threads in Java

1. **By Extending `Thread` Class**
    ```java
    class MyThread extends Thread {
        public void run() {
            System.out.println("Thread running");
        }
    }
    // Usage:
    MyThread t = new MyThread();
    t.start();
    ```

2. **By Implementing `Runnable` Interface**
    ```java
    class MyRunnable implements Runnable {
        public void run() {
            System.out.println("Runnable running");
        }
    }
    // Usage:
    Thread t = new Thread(new MyRunnable());
    t.start();
    ```

---

## Thread Lifecycle

- **States:** New → Runnable → Running → Blocked/Waiting → Dead (Terminated)

---

## Thread Methods

- `start()`: Begins thread execution (calls `run()` in new thread)
- `run()`: Entry point for thread logic (don’t call directly)
- `sleep(ms)`: Pause thread for specified time
- `join()`: Wait for thread to finish
- `yield()`: Pause and allow other threads to execute
- `setPriority()`: Set thread priority (1-10)

---

## Synchronization

- **Why Needed:** To prevent thread interference and ensure data consistency when multiple threads access shared resources.
- **How:** Using `synchronized` keyword.

**Example:**
```java
class Counter {
    private int count = 0;
    public synchronized void increment() {
        count++;
    }
}
```

- **Synchronized Block:**
    ```java
    synchronized (this) {
        // synchronized code
    }
    ```

- **Static Synchronization:** Lock on class object.
    ```java
    static synchronized void staticMethod() { }
    ```

---

## Inter-Thread Communication

- **Methods:** `wait()`, `notify()`, `notifyAll()` (must be called inside synchronized context)
- **Purpose:** Cooperating between threads (e.g., producer-consumer problem)

---

## Deadlock

- **Definition:** Situation where two or more threads are blocked forever, waiting for each other.
- **How to Avoid:** Lock ordering, using tryLock (from `java.util.concurrent.locks`), minimizing synchronized scope.

---

## Interview Tips

- Be able to explain thread lifecycle and state transitions.
- Know how to create threads both ways (Thread, Runnable).
- Explain why synchronization is needed, and where deadlocks can occur.
- Be familiar with high-level concurrency utilities: `ExecutorService`, `Callable`, `Future`, etc.

---

## Possible Follow-Up Questions

- What is the difference between process and thread?
- Can you start a thread twice?
- What happens if you call run() instead of start()?
- How can you avoid deadlocks?
- Difference between synchronized method and synchronized block?
- What is the volatile keyword?
