# 3. Java Classes, Objects & Constructors

---

## What is a Class?

- **Definition:** A blueprint or template for creating objects.
- **Syntax:**
    ```java
    class Car {
        // fields (attributes)
        String color;
        int year;

        // methods (behavior)
        void drive() { System.out.println("Driving..."); }
    }
    ```

---

## What is an Object?

- **Definition:** A real-world entity created from a class. It occupies memory.
- **Syntax:**
    ```java
    Car myCar = new Car(); // Object creation
    myCar.color = "red";
    myCar.drive();
    ```

---

## Fields & Methods

- **Fields:** Variables that hold object state (`String color; int year;`)
- **Methods:** Functions that define object behavior (`void drive()`)

---

## Constructors

- **Definition:** Special methods with the same name as the class, called automatically when an object is created.
- **Purpose:** Initialize object state.
- **Types:**
    - **Default Constructor:** No arguments, provided by Java if you don't define any.
    - **Parameterized Constructor:** Accepts arguments to initialize fields.

- **Example:**
    ```java
    class Student {
        String name;
        int rollNo;

        // Default constructor
        Student() {
            name = "Unknown";
            rollNo = 0;
        }

        // Parameterized constructor
        Student(String n, int r) {
            name = n;
            rollNo = r;
        }
    }
    ```

---

## Constructor Overloading

- Multiple constructors with different parameter lists in the same class.
    ```java
    class Box {
        int length, width;
        Box() { length = 1; width = 1; }
        Box(int l, int w) { length = l; width = w; }
    }
    ```

---

## Key Points

- Constructors don’t have a return type (not even `void`).
- If you define any constructor, Java does **not** supply a default one.
- Objects are always created with `new` in Java.

---

## Interview Tips

- Understand memory allocation for objects vs. primitive variables.
- Be ready to explain the difference between methods and constructors.
- Know what happens if you don’t define any constructor.

---

## Possible Follow-Up Questions

- What is the difference between a class and an object?
- Can you overload constructors in Java?
- What is the default value of object references in Java?
- What happens if you forget to use the `new` keyword?
