### 💡 **Aim:**
Write programs for implementation of **throw** and **throws** clauses in Java.

---

### 📘 **Theory:**

In Java, exceptions can be explicitly thrown using the `throw` keyword and can be declared to be thrown by methods using the `throws` keyword.

- **`throw` keyword**: It is used to explicitly throw an exception. The `throw` statement is followed by an instance of the exception class.

  **Syntax:**
  ```java
  throw new ExceptionType("Error Message");
  ```

- **`throws` keyword**: It is used in the method signature to declare that a method might throw one or more exceptions. This tells the calling method that it needs to handle those exceptions.

  **Syntax:**
  ```java
  public void methodName() throws ExceptionType {
      // code that might throw an exception
  }
  ```

---

### 💻 **Program:**

**1. Program using `throw` to explicitly throw an exception:**

```java
public class ThrowExample {
    // Method to check the age
    public static void checkAge(int age) {
        if (age < 18) {
            // Throwing an exception manually if the age is less than 18
            throw new ArithmeticException("Age must be 18 or older.");
        } else {
            System.out.println("Access granted.");
        }
    }

    public static void main(String[] args) {
        try {
            checkAge(15);  // Passing an invalid age
        } catch (ArithmeticException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}
```

**Explanation:**
- In the `checkAge` method, we use the `throw` keyword to throw an `ArithmeticException` when the age is less than 18.
- The exception is caught in the `catch` block, and the error message is displayed.

---

**2. Program using `throws` to declare exceptions in method signature:**

```java
public class ThrowsExample {

    // Method that throws an exception
    public static void divideNumbers(int a, int b) throws ArithmeticException {
        if (b == 0) {
            // Throwing an ArithmeticException if dividing by zero
            throw new ArithmeticException("Cannot divide by zero.");
        } else {
            System.out.println("Result: " + (a / b));
        }
    }

    public static void main(String[] args) {
        try {
            // Calling method that can throw an exception
            divideNumbers(10, 0);  // Dividing by zero
        } catch (ArithmeticException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}
```

**Explanation:**
- The method `divideNumbers` declares that it may throw an `ArithmeticException` using the `throws` keyword.
- In the `main` method, we call `divideNumbers` with a denominator of 0, which triggers the exception.

---

### 🖥️ **Output:**

**Output for the first program (using `throw`):**

```
Exception: Age must be 18 or older.
```

**Output for the second program (using `throws`):**

```
Exception: Cannot divide by zero.
```

---

### ✅ **Conclusion:**

- The **`throw`** keyword is used to explicitly throw an exception during the execution of the program when a certain condition is met.
- The **`throws`** keyword is used to declare that a method may throw one or more exceptions, and the calling method must handle or declare them.
  
Both **`throw`** and **`throws`** are powerful tools for exception handling, allowing you to create robust, fault-tolerant programs.
