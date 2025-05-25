# 5. Inheritance & Method Overriding

---

## Inheritance in Java

- **Definition:** Mechanism by which one class (child/subclass) acquires properties and behaviors (fields & methods) of another class (parent/superclass).
- **Purpose:** Code reusability, logical hierarchy, and method extension.
- **Types Supported in Java:**
  - **Single Inheritance:** One subclass inherits from one superclass.
  - **Multilevel Inheritance:** A class extends a class, which extends another class.
  - **Hierarchical Inheritance:** Multiple subclasses inherit from one superclass.
- **Not Supported Directly:** Multiple inheritance (with classes) — use interfaces.

**Syntax Example:**
```java
class Animal {
    void eat() { System.out.println("eating..."); }
}
class Dog extends Animal {
    void bark() { System.out.println("barking..."); }
}
```
---

## Method Overriding

- **Definition:** Subclass provides a specific implementation for a method already defined in its parent class.
- **Rules:**
  - Method name, return type, and parameters must be the same as in the parent class.
  - Access modifier can be the same or more visible.
  - Cannot override `final` or `static` methods.
  - Use `@Override` annotation for clarity (optional but recommended).

**Example:**
```java
class Animal {
    void sound() { System.out.println("Animal sound"); }
}
class Dog extends Animal {
    @Override
    void sound() { System.out.println("Woof!"); }
}
```

---

## Super Keyword

- **Purpose:** Refers to the parent class (superclass) object.
- **Uses:**
  - Access superclass methods/fields.
  - Call parent constructor.

**Example:**
```java
class Animal {
    void eat() { System.out.println("eating"); }
}
class Dog extends Animal {
    void eat() { System.out.println("eating dog food"); }
    void printBoth() {
        eat();      // Dog's eat
        super.eat(); // Animal's eat
    }
}
```

---

## Constructor Chaining

- **When subclass object is created:**  
  1. Superclass constructor is called first (explicitly via `super(...)` or implicitly).
  2. Then subclass constructor runs.

---

## Interview Tips

- Be ready to explain why Java does not allow multiple inheritance with classes (ambiguity/"diamond problem").
- Know when and why to use `super`.
- Distinguish method **overriding** vs. **overloading**.

---

## Possible Follow-Up Questions

- What is the diamond problem? How does Java solve it?
- Can you override static or private methods?
- What is the use of `super()` in constructors?
- What is the difference between method overriding and method hiding?
