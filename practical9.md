### 💡 **Aim:**
Develop a program for the implementation of the **interface** in Java.

---

### 📘 **Theory:**

An **interface** in Java is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. Interfaces cannot contain instance fields or constructors. A class that implements an interface must implement all of the methods defined in the interface, unless the class is abstract.

**Key points:**
- An interface defines a contract of what a class can do but not how it does it.
- A class implements an interface using the `implements` keyword.
- A class can implement multiple interfaces (Java supports multiple inheritance via interfaces).

---

### 💻 **Program:**

```java
// Defining an interface
interface Animal {
    void sound();  // Abstract method
    void eat();    // Abstract method
}

// Implementing the interface in a class
class Dog implements Animal {
    // Implementing the abstract methods
    public void sound() {
        System.out.println("The dog barks.");
    }

    public void eat() {
        System.out.println("The dog eats dog food.");
    }
}

class Cat implements Animal {
    // Implementing the abstract methods
    public void sound() {
        System.out.println("The cat meows.");
    }

    public void eat() {
        System.out.println("The cat eats cat food.");
    }
}

public class InterfaceDemo {
    public static void main(String[] args) {
        // Creating objects of classes that implement the Animal interface
        Animal dog = new Dog();
        Animal cat = new Cat();

        // Calling methods defined in the Animal interface
        dog.sound();
        dog.eat();

        cat.sound();
        cat.eat();
    }
}
```

---

### 🖥️ **Output:**

```
The dog barks.
The dog eats dog food.
The cat meows.
The cat eats cat food.
```

---

### ✅ **Conclusion:**

This program demonstrates the implementation of an interface in Java. The `Animal` interface defines two abstract methods (`sound()` and `eat()`), and the classes `Dog` and `Cat` implement these methods. By using interfaces, we can define behavior in a common contract and allow multiple classes to provide their own implementations of that behavior, promoting flexibility and scalability in the code.
