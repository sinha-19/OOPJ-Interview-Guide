# 9. Java Collections Framework

---

## What is the Collections Framework?

- **Definition:** A unified architecture for storing and manipulating groups of objects.
- **Purpose:** Provides ready-to-use data structures (lists, sets, maps, queues) and algorithms for searching, sorting, etc.

---

## Core Interfaces

| Interface  | Implementations        | Description                     |
|------------|-----------------------|---------------------------------|
| List       | ArrayList, LinkedList | Ordered, allows duplicates      |
| Set        | HashSet, TreeSet      | Unordered, no duplicates        |
| Queue      | LinkedList, PriorityQueue | FIFO, special orderings    |
| Map        | HashMap, TreeMap      | Key-value pairs, no duplicate keys |

---

## List Example

```java
import java.util.*;
List<String> names = new ArrayList<>();
names.add("Alice");
names.add("Bob");
System.out.println(names.get(0)); // Alice
```

---

## Set Example

```java
Set<Integer> numbers = new HashSet<>();
numbers.add(1);
numbers.add(2);
numbers.add(1); // Duplicate, ignored
System.out.println(numbers.size()); // 2
```

---

## Map Example

```java
Map<String, Integer> ages = new HashMap<>();
ages.put("Tom", 20);
ages.put("Jerry", 25);
System.out.println(ages.get("Tom")); // 20
```

---

## Queue Example

```java
Queue<Integer> queue = new LinkedList<>();
queue.add(10);
queue.add(20);
System.out.println(queue.poll()); // 10
```

---

## Key Points

- **ArrayList:** Fast random access, slow insert/delete in middle.
- **LinkedList:** Fast insert/delete, slower random access.
- **HashSet/HashMap:** Fast access, unordered.
- **TreeSet/TreeMap:** Sorted order, slower than hash-based.

---

## Generics

- Allow type-safe collections (no casting required).
- Example: `List<String>`, not just `List`.

---

## Common Algorithms

- Sorting: `Collections.sort(list);`
- Searching: `Collections.binarySearch(list, key);`
- Shuffle: `Collections.shuffle(list);`

---

## Interview Tips

- Know the difference between List, Set, Queue, and Map.
- Be able to choose the right implementation for a scenario.
- Understand how generics improve safety and why raw types are discouraged.

---

## Possible Follow-Up Questions

- What is the difference between HashMap and TreeMap?
- When would you use a Set over a List?
- Explain fail-fast vs. fail-safe iterators.
- How would you sort a list of custom objects?
