### 💡 **Aim:**
Develop a program for implementing **different types of constructors**.

---

### 📘 **Theory:**

A **constructor** in Java is a special method that is used to initialize objects. It is called when an object of a class is created.

**Types of constructors:**
1. **Default Constructor** – No arguments, initializes with default values.
2. **Parameterized Constructor** – Takes arguments to set custom values.
3. **Copy Constructor** (manually defined in Java) – Creates a new object by copying another object's values.

---

### 💻 **Program:**

```java
class Student {
    int rollNo;
    String name;

    // Default Constructor
    Student() {
        rollNo = 0;
        name = "Unknown";
    }

    // Parameterized Constructor
    Student(int r, String n) {
        rollNo = r;
        name = n;
    }

    // Copy Constructor
    Student(Student s) {
        rollNo = s.rollNo;
        name = s.name;
    }

    void display() {
        System.out.println("Roll No: " + rollNo + ", Name: " + name);
    }
}

public class ConstructorDemo {
    public static void main(String[] args) {
        Student s1 = new Student();                      // Default constructor
        Student s2 = new Student(101, "Vaibhav");        // Parameterized constructor
        Student s3 = new Student(s2);                    // Copy constructor

        System.out.println("Student 1:");
        s1.display();

        System.out.println("Student 2:");
        s2.display();

        System.out.println("Student 3 (copy of Student 2):");
        s3.display();
    }
}
```

---

### 🖥️ **Output:**

```
Student 1:
Roll No: 0, Name: Unknown

Student 2:
Roll No: 101, Name: Vaibhav

Student 3 (copy of Student 2):
Roll No: 101, Name: Vaibhav
```

---

### ✅ **Conclusion:**

This program demonstrates the use of different constructors in Java. Default constructors initialize values with defaults, parameterized constructors allow custom initialization, and copy constructors help duplicate object data. Mastering constructors is essential for effective object-oriented programming.
