### 💡 **Aim:**
Write programs for implementation of **try**, **catch**, and **finally** blocks in Java.

---

### 📘 **Theory:**

In Java, exceptions are handled using **try**, **catch**, and **finally** blocks:

1. **try block**: It is used to enclose the code that might throw an exception.
2. **catch block**: It is used to handle the exception that occurs in the try block. It catches the exception object and handles it.
3. **finally block**: It is always executed after the execution of the try and catch blocks, whether an exception is thrown or not. It is used for clean-up operations like closing a file or releasing resources.

**Syntax:**
```java
try {
    // Code that might throw an exception
} catch (ExceptionType e) {
    // Code to handle the exception
} finally {
    // Code that will always execute
}
```

---

### 💻 **Program:**

**1. Basic example with try, catch, and finally:**

```java
public class TryCatchFinallyExample {
    public static void main(String[] args) {
        try {
            // Trying to divide by zero
            int result = 10 / 0;
            System.out.println("Result: " + result);  // This line won't be executed
        } catch (ArithmeticException e) {
            // Catching ArithmeticException
            System.out.println("Error: Division by zero is not allowed.");
        } finally {
            // This block will always execute
            System.out.println("Finally block is executed.");
        }
    }
}
```

**Explanation:**
- The code in the `try` block attempts to divide by zero, which will throw an `ArithmeticException`.
- The `catch` block catches this exception and prints an error message.
- The `finally` block is executed regardless of whether an exception occurred or not.

---

**2. Example with multiple exceptions and finally block:**

```java
public class MultipleCatchFinallyExample {
    public static void main(String[] args) {
        try {
            String str = null;
            System.out.println(str.length());  // This will throw NullPointerException
        } catch (NullPointerException e) {
            // Catching NullPointerException
            System.out.println("Error: Null pointer exception occurred.");
        } catch (Exception e) {
            // Catching any other exception
            System.out.println("Error: An unknown exception occurred.");
        } finally {
            // This block will always execute
            System.out.println("Finally block executed regardless of the exception.");
        }
    }
}
```

**Explanation:**
- The code in the `try` block throws a `NullPointerException` by trying to call `length()` on a null object.
- The `catch` block catches the `NullPointerException` and prints the message.
- The `finally` block is executed after the `catch` block.

---

### 🖥️ **Output:**

**Output for the first program:**

```
Error: Division by zero is not allowed.
Finally block is executed.
```

**Output for the second program:**

```
Error: Null pointer exception occurred.
Finally block executed regardless of the exception.
```

---

### ✅ **Conclusion:**

- The **try** block is used to write the code that might cause an exception.
- The **catch** block handles specific exceptions and prevents the program from crashing.
- The **finally** block is executed regardless of whether an exception occurred or not, making it ideal for clean-up code.
  
This structure ensures that exceptions are handled gracefully and that resources are properly managed, even in the event of an exception.
