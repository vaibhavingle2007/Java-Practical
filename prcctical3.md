Sure, here’s the **full practical write-up** for:

---

### 💡 **Aim:**
Write programs to demonstrate the use of: **if statements** in Java.

---

### 📘 **Theory:**

The `if` statement is a basic control structure in Java used to execute a block of code only if a specified condition is true. It's used for decision-making in programs.

**Types of `if` statements:**
1. **Simple if** – Executes code when condition is true.
2. **if-else** – Chooses between two paths based on condition.
3. **if-else-if ladder** – Selects one of multiple conditions.

These help control the logical flow based on runtime data.

---

### 💻 **Program:**

```java
import java.util.Scanner;

public class IfStatementExample {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter an integer: ");
        int number = input.nextInt();

        // Simple if
        if (number > 0) {
            System.out.println("The number is positive.");
        }

        // if-else
        if (number % 2 == 0) {
            System.out.println("The number is even.");
        } else {
            System.out.println("The number is odd.");
        }

        // if-else-if ladder
        if (number > 0) {
            System.out.println("It is a positive number.");
        } else if (number < 0) {
            System.out.println("It is a negative number.");
        } else {
            System.out.println("The number is zero.");
        }

        input.close();
    }
}
```

---

### 🖥️ **Output:**

**Example 1:**
```
Enter an integer: 7  
The number is positive.  
The number is odd.  
It is a positive number.
```

**Example 2:**
```
Enter an integer: -2  
The number is even.  
It is a negative number.
```

**Example 3:**
```
Enter an integer: 0  
The number is even.  
The number is zero.
```

---

### ✅ **Conclusion:**

This program demonstrates different uses of `if` statements in Java. It highlights how decisions in logic can be made using simple, nested, and laddered conditions based on runtime input, making the program adaptive and responsive.

---

Want me to write the next one? Just give the topic or aim.
