# 10. Inner Classes, Anonymous Classes & Lambda Expressions

---

## Inner Classes

- **Definition:** A class defined within another class.
- **Purpose:** Logical grouping, encapsulation, can access enclosing class members.

### Types:

1. **Member Inner Class**  
   Defined at class level, outside any method.
   ```java
   class Outer {
       class Inner {
           void show() { System.out.println("Hello from Inner"); }
       }
   }
   ```
   Usage: `Outer.Inner in = new Outer().new Inner();`

2. **Static Nested Class**  
   Declared with `static` keyword, cannot access non-static members of outer class.
   ```java
   class Outer {
       static class Nested {
           void show() { System.out.println("Static Nested"); }
       }
   }
   ```
   Usage: `Outer.Nested n = new Outer.Nested();`

3. **Local Inner Class**  
   Defined inside a method.
   ```java
   void myMethod() {
       class Local { void msg() { System.out.println("Local"); } }
       new Local().msg();
   }
   ```

---

## Anonymous Classes

- **Definition:** Local class without a name, declared and instantiated in a single statement.
- **Purpose:** Useful for quick implementation of interfaces/abstract classes, often in event handling or callbacks.

**Example with Interface:**
```java
Runnable r = new Runnable() {
    public void run() {
        System.out.println("Running anonymously");
    }
};
```

**Example with Abstract Class:**
```java
abstract class Animal { abstract void sound(); }
Animal a = new Animal() {
    void sound() { System.out.println("Meow"); }
};
```

---

## Lambda Expressions (Java 8+)

- **Definition:** Short, clear way to implement functional interfaces (interfaces with a single abstract method).
- **Purpose:** Reduce boilerplate for anonymous classes, especially in functional-style programming.

**Syntax:**  
`(parameters) -> { body }`

**Example:**
```java
interface Addable { int add(int a, int b); }
Addable sum = (a, b) -> a + b;
System.out.println(sum.add(5, 7)); // 12
```

**Use with Collections:**
```java
List<String> names = Arrays.asList("A", "B", "C");
names.forEach(name -> System.out.println(name));
```

---

## Interview Tips

- Know syntax and use cases for all inner class types.
- Understand when to use anonymous classes vs. lambda expressions.
- Be prepared to explain functional interfaces.
- Lambda expressions cannot be used for interfaces with more than one abstract method.

---

## Possible Follow-Up Questions

- What are the differences between member and static nested classes?
- Can a local inner class access local variables of the method?
- What is a functional interface? Name some built-in ones.
- How do lambda expressions improve code readability?
- Where are anonymous classes commonly used?
