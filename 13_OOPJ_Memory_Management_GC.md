# 13. Java Memory Management & Garbage Collection

---

## Java Memory Management

- **Memory Areas:**
  - **Heap:** Stores objects and instance variables (shared by all threads).
  - **Stack:** Stores method calls and local variables (per thread).
  - **Method Area (MetaSpace):** Stores class metadata, static variables.
  - **PC Register:** Tracks current instruction for each thread.
  - **Native Method Stack:** For native (non-Java) methods.

---

## Object Creation & Lifetime

- Objects are created on the heap using `new`.
- Reference variables can be on stack or heap.
- When an object is no longer referenced, it becomes eligible for garbage collection.

---

## Garbage Collection (GC)

- **Purpose:** Automatically frees memory by destroying unreachable objects.
- **How:** JVM periodically runs GC thread.
- **No guarantee** of immediate GC or object finalization.

**Requesting GC:**
```java
System.gc(); // Suggests JVM to perform GC (not guaranteed)
```

---

## Finalization

- **`finalize()` method:** Called by GC before object is removed.  
  - Deprecated in Java 9+, not recommended for clean-up.
- **Better Practice:** Use `try-with-resources` and explicit resource management.

---

## Strong, Weak, Soft, and Phantom References

- **Strong Reference:** Normal reference, prevents GC.
- **Weak Reference:** Does not prevent GC (useful for caches).
- **Soft Reference:** GC’d only if memory is low.
- **Phantom Reference:** Used for post-mortem cleanup actions.

---

## Memory Leaks in Java

- Can occur if references to unused objects are unintentionally held (e.g., static collections).
- Use profilers (`jvisualvm`, `jconsole`) to debug.

---

## Interview Tips

- Be able to draw the JVM memory map (heap, stack, etc.).
- Know what triggers garbage collection and how to avoid memory leaks.
- Explain difference between `finalize()` and explicit clean-up.
- Understand types of references and their use cases.

---

## Possible Follow-Up Questions

- What happens if you call `System.gc()`?
- Why is `finalize()` deprecated?
- How do you detect and prevent memory leaks in Java?
- What is the difference between stack and heap memory?
- What are weak references used for?
