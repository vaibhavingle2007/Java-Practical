### 💡 **Aim:**
Write programs to demonstrate the use of: **Built-in packages** and **User-defined packages** in Java.

---

### 📘 **Theory:**

**Built-in Packages:**
Java provides a rich set of pre-defined packages that contain classes and interfaces for performing various tasks. These packages are available by default in the Java API. Examples include:
- `java.util` for utility classes like `ArrayList`, `HashMap`, etc.
- `java.io` for input/output operations.
- `java.lang` for fundamental classes like `String`, `Math`, etc.

**User-defined Packages:**
Java allows you to create your own packages to organize your code. Packages are used to group related classes and interfaces, avoiding name conflicts and making code more maintainable. You define a package using the `package` keyword at the top of the class file.

**Syntax for creating a package:**
```java
package myPackage;
class MyClass { ... }
```

---

### 💻 **Program:**

**1. Program to demonstrate Built-in Packages:**

```java
import java.util.Scanner;  // Importing built-in Scanner class from java.util package

public class BuiltInPackageDemo {
    public static void main(String[] args) {
        // Using Scanner class to take user input
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.println("Hello, " + name + "!");
        scanner.close();
    }
}
```

**Explanation:**
- Here, we are using the `Scanner` class from the `java.util` package, which is a built-in package, to take user input.

---

**2. Program to demonstrate User-defined Packages:**

First, create a package by saving the file in a specific directory. Let's say you want to create a package called `mypackage` and store classes within it.

**File 1: `Greeting.java` in `mypackage`**

```java
package mypackage;  // Define the package

public class Greeting {
    public void sayHello(String name) {
        System.out.println("Hello, " + name + "!");
    }
}
```

**File 2: `TestPackage.java` in the default package**

```java
import mypackage.Greeting;  // Import the user-defined package

public class TestPackage {
    public static void main(String[] args) {
        // Creating an object of Greeting class from the user-defined package
        Greeting greet = new Greeting();
        greet.sayHello("Vaibhav");
    }
}
```

**Directory Structure:**
```
your_project/
├── mypackage/
│   └── Greeting.java
└── TestPackage.java
```

---

### 🖥️ **Output:**

**Output for Built-in Package:**

```
Enter your name: Vaibhav
Hello, Vaibhav!
```

**Output for User-defined Package:**

```
Hello, Vaibhav!
```

---

### ✅ **Conclusion:**

- The **Built-in Package** example demonstrates the use of the `Scanner` class from the `java.util` package to read user input.
- The **User-defined Package** example shows how to create a custom package (`mypackage`) and use it in other classes. The `Greeting` class, which is part of the `mypackage`, is used in the `TestPackage` class to print a greeting message.

Packages, whether built-in or user-defined, help organize code, avoid conflicts, and improve maintainability and scalability.
