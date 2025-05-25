# 2. Core OOP Concepts (Encapsulation, Inheritance, Polymorphism, Abstraction)

---

## 1. Encapsulation

- **Definition:** Wrapping data (variables) and code (methods) together as a single unit (class), and restricting access to some components.
- **Purpose:** Protects data from outside interference and misuse.
- **How in Java:**  
  - Use `private` variables and provide `public` getter/setter methods.
- **Example:**
    ```java
    class Student {
        private int age; // Encapsulated field

        public int getAge() { return age; }
        public void setAge(int age) { this.age = age; }
    }
    ```

---

## 2. Inheritance

- **Definition:** Mechanism where one class acquires the fields and methods of another.
- **Purpose:** Promotes code reuse and establishes a relationship between parent and child classes.
- **Types in Java:** Single, Multilevel, Hierarchical (Java does NOT support multiple inheritance with classes).
- **Syntax:** `class Child extends Parent { }`
- **Example:**
    ```java
    class Animal {
        void eat() { System.out.println("eating"); }
    }
    class Dog extends Animal {
        void bark() { System.out.println("barking"); }
    }
    ```

---

## 3. Polymorphism

- **Definition:** Ability of an object to take many forms; same interface, different implementations.
- **Types in Java:**
    - **Compile-Time (Static):** Method Overloading
    - **Run-Time (Dynamic):** Method Overriding
- **Example:**
    ```java
    // Overloading
    class MathUtil {
        int add(int a, int b) { return a + b; }
        double add(double a, double b) { return a + b; }
    }
    // Overriding
    class Animal {
        void sound() { System.out.println("Animal sound"); }
    }
    class Cat extends Animal {
        void sound() { System.out.println("Meow"); }
    }
    ```

---

## 4. Abstraction

- **Definition:** Hiding internal details and showing only essential features.
- **Purpose:** Reduces complexity, increases efficiency.
- **How in Java:** Using abstract classes and interfaces.
- **Example:**
    ```java
    abstract class Shape {
        abstract void draw();  // Abstract method (no body)
    }
    class Circle extends Shape {
        void draw() { System.out.println("Drawing Circle"); }
    }
    ```

---

## Summary Table

| Concept        | What it Means                       | Java Example                   |
|----------------|-------------------------------------|-------------------------------|
| Encapsulation  | Data hiding within classes          | Private fields + getters/setters |
| Inheritance    | Reusing parent class features       | `extends` keyword             |
| Polymorphism   | Many forms (overloading/overriding) | Method overloading/overriding |
| Abstraction    | Essential features only             | Abstract class/interface      |

---

## Interview Tips

- Be able to define and differentiate all four OOP pillars.
- Give simple code examples (not just definitions) in Java.
- Know practical uses: e.g., why use abstraction or encapsulation?
- Understand method overloading vs. overriding in detail.

---

## Possible Follow-Up Questions

- How is abstraction achieved in Java?
- What is the difference between encapsulation and abstraction?
- Why does Java not support multiple inheritance (with classes)?
- Give real-world analogies for each OOP concept.
