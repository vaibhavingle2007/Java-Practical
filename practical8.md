### 💡 **Aim:**
Develop a program to implement: **Single Inheritance** and **Multilevel Inheritance**.

---

### 📘 **Theory:**

- **Single Inheritance**: Involves a class inheriting the properties and behaviors (fields and methods) of a single parent class.
  
  **Syntax:**
  ```java
  class Parent { ... }
  class Child extends Parent { ... }
  ```

- **Multilevel Inheritance**: A class inherits from another class, which itself is derived from a third class. This creates a chain of inheritance.

  **Syntax:**
  ```java
  class Grandparent { ... }
  class Parent extends Grandparent { ... }
  class Child extends Parent { ... }
  ```

---

### 💻 **Program:**

```java
// Single Inheritance
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

// Multilevel Inheritance
class Vehicle {
    void move() {
        System.out.println("The vehicle moves.");
    }
}

class Car extends Vehicle {
    void speed() {
        System.out.println("The car is fast.");
    }
}

class ElectricCar extends Car {
    void charge() {
        System.out.println("The electric car is charging.");
    }
}

public class InheritanceDemo {
    public static void main(String[] args) {
        
        // Single Inheritance
        System.out.println("--- Single Inheritance ---");
        Dog dog = new Dog();
        dog.eat(); // Inherited from Animal class
        dog.bark(); // Defined in Dog class

        // Multilevel Inheritance
        System.out.println("\n--- Multilevel Inheritance ---");
        ElectricCar eCar = new ElectricCar();
        eCar.move();  // Inherited from Vehicle class
        eCar.speed(); // Inherited from Car class
        eCar.charge(); // Defined in ElectricCar class
    }
}
```

---

### 🖥️ **Output:**

```
--- Single Inheritance ---
This animal eats food.
The dog barks.

--- Multilevel Inheritance ---
The vehicle moves.
The car is fast.
The electric car is charging.
```

---

### ✅ **Conclusion:**

This program demonstrates **Single Inheritance**, where a class `Dog` inherits from the class `Animal`, and **Multilevel Inheritance**, where `ElectricCar` inherits from `Car`, which in turn inherits from `Vehicle`. Inheritance allows classes to reuse the properties and behaviors of other classes, supporting code reusability and modularity.
