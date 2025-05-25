# 8. Exception Handling in Java

---

## What is Exception Handling?

- **Definition:** A mechanism to handle runtime errors, so program flow can be maintained.
- **Purpose:** Prevent program crashes and provide meaningful error messages.

---

## Types of Exceptions

| Type           | Description                                | Example                    |
|----------------|--------------------------------------------|----------------------------|
| Checked        | Checked at compile time                    | `IOException`, `SQLException` |
| Unchecked      | Checked at runtime (subclass of `RuntimeException`) | `NullPointerException`, `ArithmeticException` |
| Errors         | Serious issues, not meant to be handled    | `OutOfMemoryError`         |

---

## Exception Hierarchy

```
Throwable
 ├── Exception
 │    ├── IOException
 │    ├── SQLException
 │    └── RuntimeException
 │         ├── NullPointerException
 │         └── ArithmeticException
 └── Error
      ├── OutOfMemoryError
      └── StackOverflowError
```

---

## Exception Handling Keywords

- `try` – Enclose code that might throw an exception.
- `catch` – Handle the exception.
- `finally` – Block that always executes (cleanup code).
- `throw` – Manually throw an exception.
- `throws` – Declare an exception in method signature.

**Example:**
```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero!");
} finally {
    System.out.println("Cleanup code runs here.");
}
```

---

## Custom Exceptions

- **Create by extending the `Exception` class.**

```java
class MyException extends Exception {
    public MyException(String message) {
        super(message);
    }
}
```

---

## Interview Tips

- Know which exceptions are checked and unchecked.
- Understand difference between `throw` and `throws`.
- Be able to explain finally block use.
- Remember: Multiple catch blocks can be used; they are checked top-down.

---

## Possible Follow-Up Questions

- What is the difference between checked and unchecked exceptions?
- Can you catch multiple exceptions in a single catch block?
- What happens if both catch and finally have a return statement?
- Why is exception handling important in enterprise applications?
- How do you create a custom exception?
