### 💡 **Aim:**
Write programs for implementing different methods of **String class** and **StringBuffer class** in Java.

---

### 📘 **Theory:**

Java provides two main classes to work with text:

1. **String class** (immutable): Once created, the value of a `String` object cannot be changed. Methods include:
   - `length()`, `charAt()`, `substring()`, `toUpperCase()`, `toLowerCase()`, `indexOf()`, `equals()`, `concat()`

2. **StringBuffer class** (mutable): Used for creating modifiable string objects. Methods include:
   - `append()`, `insert()`, `replace()`, `delete()`, `reverse()`, `capacity()`, `setCharAt()`

---

### 💻 **Program:**

```java
public class StringDemo {
    public static void main(String[] args) {

        // String class methods
        String str = "Java Programming";

        System.out.println("Original String: " + str);
        System.out.println("Length: " + str.length());
        System.out.println("Character at index 5: " + str.charAt(5));
        System.out.println("Substring (5, 16): " + str.substring(5, 16));
        System.out.println("Uppercase: " + str.toUpperCase());
        System.out.println("Lowercase: " + str.toLowerCase());
        System.out.println("Index of 'P': " + str.indexOf('P'));
        System.out.println("Equals 'Java Programming': " + str.equals("Java Programming"));
        System.out.println("Concatenation: " + str.concat(" is powerful"));

        System.out.println("\n--- StringBuffer class ---");

        // StringBuffer class methods
        StringBuffer sb = new StringBuffer("Hello");

        System.out.println("Original StringBuffer: " + sb);
        sb.append(" World");
        System.out.println("After append: " + sb);
        sb.insert(5, ",");
        System.out.println("After insert: " + sb);
        sb.replace(6, 11, "Java");
        System.out.println("After replace: " + sb);
        sb.delete(5, 10);
        System.out.println("After delete: " + sb);
        sb.reverse();
        System.out.println("After reverse: " + sb);
        System.out.println("Capacity: " + sb.capacity());
    }
}
```

---

### 🖥️ **Output:**

```
Original String: Java Programming  
Length: 16  
Character at index 5: P  
Substring (5, 16): Programming  
Uppercase: JAVA PROGRAMMING  
Lowercase: java programming  
Index of 'P': 5  
Equals 'Java Programming': true  
Concatenation: Java Programming is powerful  

--- StringBuffer class ---
Original StringBuffer: Hello  
After append: Hello World  
After insert: Hello, World  
After replace: Hello,Java  
After delete: Helloa  
After reverse: aolleH  
Capacity: 21
```

---

### ✅ **Conclusion:**

The program effectively demonstrates various methods of the `String` and `StringBuffer` classes. `String` provides powerful tools for working with immutable text, while `StringBuffer` is suitable for modifying text dynamically. Mastering both is essential for string manipulation in Java.
