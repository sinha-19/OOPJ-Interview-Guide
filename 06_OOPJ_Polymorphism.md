# 6. Polymorphism (Compile Time & Run Time)

---

## What is Polymorphism?

- **Definition:** The ability of a variable, function, or object to take on multiple forms.
- **Purpose:** Enables flexibility and reusability in code by allowing the same interface to be used for different underlying forms (data types).

---

## Types of Polymorphism in Java

### 1. Compile-Time Polymorphism (Static Polymorphism)
- **Achieved By:** Method Overloading
- **Resolution:** Determined at compile time.
- **Example:**
    ```java
    class MathUtil {
        int add(int a, int b) { return a + b; }
        double add(double a, double b) { return a + b; }
    }
    // Usage:
    MathUtil m = new MathUtil();
    m.add(2, 3);      // Calls int version
    m.add(2.0, 3.0);  // Calls double version
    ```
- **Key Point:** Same method name, different parameter lists within the same class.

---

### 2. Run-Time Polymorphism (Dynamic Polymorphism)
- **Achieved By:** Method Overriding
- **Resolution:** Determined at runtime via dynamic method dispatch.
- **Example:**
    ```java
    class Animal {
        void sound() { System.out.println("Animal sound"); }
    }
    class Dog extends Animal {
        void sound() { System.out.println("Woof"); }
    }
    Animal ref = new Dog();
    ref.sound(); // Output: Woof
    ```
- **Key Point:** Same method signature, different implementations in subclass. The reference type determines what is accessible, but the object type determines which method gets called.

---

## Benefits of Polymorphism

- Code reusability and maintainability.
- Flexibility to introduce new classes with minimal changes.
- Enables loose coupling between objects.

---

## Real-World Analogy

- A single "remote control" (interface) can operate different devices (TV, AC, Music System) — the actual action depends on the connected device (object).

---

## Interview Tips

- Clearly differentiate between overloading (compile time) and overriding (runtime).
- Be able to show code for both.
- Explain dynamic method dispatch (calling overridden methods at runtime).

---

## Possible Follow-Up Questions

- What happens if you overload methods with the same parameter types but different return types?
- Can you override static methods?
- What is dynamic method dispatch?
- How does Java achieve runtime polymorphism?
- Is constructor overloading a form of polymorphism?
