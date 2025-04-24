### 💡 **Aim:**
Write programs to demonstrate the use of **Array** and **Vector** in Java.

---

### 📘 **Theory:**

In Java:

- **Array** is a fixed-size container used to store multiple values of the same type. Indexing starts from 0.
  - Declared with: `int[] arr = new int[5];`
  - Elements are accessed via index like `arr[0]`.

- **Vector** is part of the **java.util** package. It’s a growable array-like structure that can store objects.
  - Supports dynamic resizing.
  - Methods: `add()`, `remove()`, `get()`, `size()`, `set()`, `contains()`

---

### 💻 **Program:**

```java
import java.util.Vector;

public class ArrayVectorDemo {
    public static void main(String[] args) {

        // Using Array
        System.out.println("--- Array Example ---");
        int[] numbers = {10, 20, 30, 40, 50};

        System.out.println("Array Elements:");
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

        // Using Vector
        System.out.println("\n--- Vector Example ---");
        Vector<String> fruits = new Vector<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");
        fruits.add("Orange");

        System.out.println("Vector Elements:");
        for (int i = 0; i < fruits.size(); i++) {
            System.out.println("Element at index " + i + ": " + fruits.get(i));
        }

        // Demonstrating vector methods
        fruits.remove("Banana");
        fruits.set(1, "Grapes");
        System.out.println("\nVector after modifications: " + fruits);
    }
}
```

---

### 🖥️ **Output:**

```
--- Array Example ---
Array Elements:
Element at index 0: 10
Element at index 1: 20
Element at index 2: 30
Element at index 3: 40
Element at index 4: 50

--- Vector Example ---
Vector Elements:
Element at index 0: Apple
Element at index 1: Banana
Element at index 2: Mango
Element at index 3: Orange

Vector after modifications: [Apple, Grapes, Orange]
```

---

### ✅ **Conclusion:**

The program shows how arrays and vectors are used to store and manage collections of data. Arrays are fixed in size and faster, while vectors offer dynamic resizing and built-in methods for easier manipulation, especially when dealing with unknown or changing amounts of data.
