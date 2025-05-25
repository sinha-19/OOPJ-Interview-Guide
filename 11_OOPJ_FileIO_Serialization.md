# 11. File I/O & Serialization

---

## File I/O in Java

- **Purpose:** Read from and write to files (text/binary).
- **Key Classes (java.io):**
  - `File`: Represents file/directory path
  - `FileReader`/`FileWriter`: Read/write text files (character streams)
  - `FileInputStream`/`FileOutputStream`: Read/write binary files (byte streams)
  - `BufferedReader`/`BufferedWriter`: Efficient text file reading/writing

### Reading a Text File Example

```java
import java.io.*;
BufferedReader reader = new BufferedReader(new FileReader("file.txt"));
String line;
while ((line = reader.readLine()) != null) {
    System.out.println(line);
}
reader.close();
```

### Writing to a Text File Example

```java
BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
writer.write("Hello, File!");
writer.newLine();
writer.close();
```

---

## Serialization

- **Definition:** Converting an object into a byte stream (for storage or transmission).
- **Purpose:** Persist objects, send objects over network.
- **To Serialize:**  
  - Class must implement `Serializable` interface (marker, no methods).
- **To Deserialize:**  
  - Convert byte stream back to object.

### Example

```java
import java.io.*;
class Student implements Serializable {
    int id;
    String name;
}

Student s = new Student();
s.id = 1; s.name = "Alice";

// Serialization
ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("stud.ser"));
out.writeObject(s);
out.close();

// Deserialization
ObjectInputStream in = new ObjectInputStream(new FileInputStream("stud.ser"));
Student s2 = (Student) in.readObject();
in.close();
```

---

## Transient Keyword

- **Purpose:** Prevents a field from being serialized.
- **Example:**
  ```java
  transient int temp; // 'temp' will not be saved during serialization
  ```

---

## Interview Tips

- Know differences between byte vs. character streams.
- Understand why and when to use serialization.
- Be able to explain the role of the `transient` keyword.
- Remember: Not all objects are serializable (objects with non-serializable fields will throw errors).

---

## Possible Follow-Up Questions

- What is the difference between FileReader and FileInputStream?
- What happens if a field is not serializable?
- Why do we need the Serializable interface?
- How do you make sure sensitive fields aren’t written to disk during serialization?
