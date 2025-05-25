# 14. Java 8+ New Features (Streams, Optional, etc.)

---

## Major Java 8 Features

### 1. Lambda Expressions

- **Purpose:** Enable functional programming, concise syntax for single-method interfaces.
- **Syntax:** `(parameters) -> expression/body`
- **Example:**
    ```java
    List<String> list = Arrays.asList("a", "b", "c");
    list.forEach(s -> System.out.println(s));
    ```

---

### 2. Functional Interfaces

- **Definition:** Interface with a single abstract method.
- **Examples:** `Runnable`, `Comparator`, `Callable`, custom interfaces annotated with `@FunctionalInterface`.

---

### 3. Streams API

- **Purpose:** Process sequences of elements (collections, arrays) in a functional style.
- **Features:**
  - Filter, map, reduce, collect, forEach, etc.
  - Lazy evaluation, parallel streams.

**Example:**
```java
List<String> names = Arrays.asList("Ann", "Bob", "Cat");
names.stream()
     .filter(n -> n.startsWith("A"))
     .forEach(System.out::println);
```

---

### 4. Optional Class

- **Purpose:** Avoid `NullPointerException` by representing optional values.
- **Example:**
    ```java
    Optional<String> name = Optional.ofNullable(getName());
    name.ifPresent(System.out::println);
    ```

---

### 5. Default & Static Methods in Interfaces

- **Purpose:** Allow methods with implementations in interfaces.
- **Syntax:**
    ```java
    interface MyIntf {
        default void foo() { }
        static void bar() { }
    }
    ```

---

### 6. Method References

- **Purpose:** Shorthand for lambda expressions that call existing methods.
- **Syntax:** `ClassName::methodName` or `object::methodName`
- **Example:**
    ```java
    names.forEach(System.out::println);
    ```

---

### 7. New Date & Time API (`java.time`)

- **Purpose:** Modern, immutable date and time handling.
- **Key Classes:** `LocalDate`, `LocalTime`, `LocalDateTime`, `Period`, `Duration`, `DateTimeFormatter`

---

### 8. Collectors

- **Purpose:** Terminal operations to collect stream results.
- **Example:**
    ```java
    List<String> newList = names.stream()
                               .filter(n -> n.length() > 2)
                               .collect(Collectors.toList());
    ```

---

## Interview Tips

- Know how to create and use streams, lambdas, and Optionals.
- Explain advantages of new Date/Time API.
- Understand when to use default/static methods in interfaces.

---

## Possible Follow-Up Questions

- What’s the difference between `findFirst()` and `findAny()` in streams?
- How would you handle null values with Optional?
- What’s the advantage of using streams over loops?
- How does parallelStream() work? When would you use it?
- Can you have state in lambda expressions?
