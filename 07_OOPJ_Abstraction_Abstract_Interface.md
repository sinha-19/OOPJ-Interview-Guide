# 7. Abstraction (Abstract Classes & Interfaces)

---

## What is Abstraction?

- **Definition:** Hiding complex implementation details and exposing only the essential features of an object.
- **Purpose:** Reduce programming complexity, focus on "what" an object does rather than "how".

---

## Achieving Abstraction in Java

### 1. Abstract Classes

- **Definition:** A class declared with the `abstract` keyword. Cannot be instantiated directly.
- **Features:**
  - Can have abstract methods (without body) and concrete methods (with body).
  - Can have fields and constructors.
  - Used when classes share some methods but also have unique implementations.

**Syntax Example:**
```java
abstract class Shape {
    abstract void draw(); // abstract method
    void show() { System.out.println("Shape"); } // concrete method
}

class Circle extends Shape {
    void draw() { System.out.println("Drawing circle"); }
}
```

---

### 2. Interfaces

- **Definition:** A reference type in Java (like a contract) with abstract methods (Java 8+ can include default and static methods).
- **Features:**
  - All methods are implicitly public and abstract (until Java 7).
  - Cannot have fields (other than static final constants).
  - Supports multiple inheritance (a class can implement multiple interfaces).

**Syntax Example:**
```java
interface Drawable {
    void draw(); // implicitly public and abstract
}

class Rectangle implements Drawable {
    public void draw() { System.out.println("Drawing rectangle"); }
}
```

---

## Abstract Class vs Interface

| Feature              | Abstract Class            | Interface                      |
|----------------------|--------------------------|--------------------------------|
| Methods              | Abstract & concrete      | Only abstract (default/static from Java 8) |
| Variables            | Any type                 | `public static final` only     |
| Constructors         | Yes                      | No                             |
| Multiple Inheritance | Not supported            | Supported (via implements)     |
| Use Case             | Shared base code         | Contract for capabilities      |

---

## Real-World Analogy

- **Abstract Class:** "Vehicle" — all vehicles can `start()` and `stop()` (implemented methods), but each defines `drive()` differently (abstract method).
- **Interface:** "Flyable" — any class that can fly (e.g., Bird, Plane) implements this capability, regardless of inheritance chain.

---

## Interview Tips

- Know when to use an abstract class vs. interface.
- Be ready to write code with both.
- Understand default and static methods in interfaces (Java 8+).
- Remember: A class can implement multiple interfaces but extend only one class.

---

## Possible Follow-Up Questions

- Can an interface extend another interface?
- Can you have a constructor in an interface?
- What’s the difference between abstract classes and interfaces?
- When would you prefer an interface over an abstract class?
