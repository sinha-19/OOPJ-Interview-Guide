# 4. Access Modifiers & Static/Final Keywords

---

## Access Modifiers in Java

- **Purpose:** Control visibility/scope of classes, fields, methods, and constructors.

| Modifier     | Same Class | Same Package | Subclass (diff pkg) | Other Packages |
|--------------|:----------:|:------------:|:-------------------:|:--------------:|
| `private`    | ✅         | ❌           | ❌                  | ❌             |
| (default)    | ✅         | ✅           | ❌                  | ❌             |
| `protected`  | ✅         | ✅           | ✅                  | ❌             |
| `public`     | ✅         | ✅           | ✅                  | ✅             |

- **Default:** No modifier = package-private (visible within package only).

**Example:**
```java
class Test {
    private int a;           // Only within Test
    int b;                   // Package-private
    protected int c;         // Package + subclasses
    public int d;            // Everywhere
}
```

---

## Static Keyword

- **Purpose:** Belongs to the class, not to any specific instance.
- **Usage:** Fields, methods, blocks, nested classes.

**Features:**
- Static members are shared among all objects.
- Can be accessed without creating an object (via `ClassName.member`).

**Example:**
```java
class Counter {
    static int count = 0;
    Counter() { count++; }
}
Counter c1 = new Counter();
Counter c2 = new Counter();
System.out.println(Counter.count); // 2
```

**Static Methods:**
- Cannot access non-static members directly.
- Can be called via class name.

```java
class MathUtil {
    static int square(int x) { return x * x; }
}
```

---

## Final Keyword

- **Purpose:** Restricts further modification.

| Usage           | Effect                                                     |
|-----------------|------------------------------------------------------------|
| `final` var     | Value cannot be changed after initialization (constant)    |
| `final` method  | Cannot be overridden in subclasses                         |
| `final` class   | Cannot be subclassed (no inheritance)                      |

**Examples:**
```java
final int x = 10;      // Constant variable
final void show() { }  // No override allowed
final class A { }      // No class can extend A
```

---

## Interview Tips

- Know visibility rules for each modifier.
- Be able to explain why/where you’d use `static` or `final`.
- Static methods: cannot use `this` or access instance (non-static) data.
- Final classes: e.g., `java.lang.String` is final.

---

## Possible Follow-Up Questions

- What is the default access modifier for class members?
- Can a class be `final` and `abstract` at once?
- What happens if you try to override a final method?
- Why are utility methods often static?
- Can static methods be overridden?
