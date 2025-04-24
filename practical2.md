
### 💡 **Aim:**
Write programs to evaluate different types of expressions in Java.

---

### 📘 **Theory:**

In Java, expressions are combinations of variables, operators, and values that yield a result. Types of expressions include:

- **Arithmetic expressions:** Use arithmetic operators (`+`, `-`, `*`, `/`, `%`)
- **Relational expressions:** Compare values using relational operators (`<`, `>`, `<=`, `>=`, `==`, `!=`)
- **Logical expressions:** Combine boolean values using logical operators (`&&`, `||`, `!`)
- **Assignment expressions:** Assign values using `=`, `+=`, `-=`, etc.

Evaluating expressions helps understand operator precedence, associativity, and data type conversions in Java.

---

### 💻 **Program:**

```java
public class ExpressionEvaluation {
    public static void main(String[] args) {
        // Arithmetic Expression
        int a = 10, b = 5, c = 2;
        int result1 = a + b * c;
        System.out.println("Arithmetic Expression (a + b * c): " + result1);

        // Relational Expression
        boolean result2 = a > b;
        System.out.println("Relational Expression (a > b): " + result2);

        // Logical Expression
        boolean x = true, y = false;
        boolean result3 = x && y;
        System.out.println("Logical Expression (x && y): " + result3);

        // Assignment Expression
        int d = 5;
        d += 3; // equivalent to d = d + 3
        System.out.println("Assignment Expression (d += 3): " + d);
    }
}
```

---

### 🖥️ **Output:**

```
Arithmetic Expression (a + b * c): 20
Relational Expression (a > b): true
Logical Expression (x && y): false
Assignment Expression (d += 3): 8
```

---

### ✅ **Conclusion:**

The program successfully demonstrates the evaluation of different types of expressions in Java, highlighting how operator precedence and data types affect the final result. Understanding these basics is crucial for writing logical and efficient Java programs.

---

Need the next one? Just tell me the aim/topic.
