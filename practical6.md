### 💡 **Aim:**
Write programs using Wrapper Class: to convert primitive into object. To convert objects into primitives.

---

### 📘 **Theory:**

Java provides **Wrapper classes** to wrap primitive data types into objects. These classes are:
- `Integer`, `Double`, `Character`, `Boolean`, etc.

**Boxing**: Converting primitive to object.  
**Unboxing**: Converting object to primitive.

Useful in collections (like `ArrayList`) which can only store objects.

---

### 💻 **Program:**

```java
public class WrapperDemo {
    public static void main(String[] args) {

        // Primitive to Object (Boxing)
        int a = 100;
        Integer objA = Integer.valueOf(a);  // explicit boxing
        Integer objAuto = a;                // auto-boxing

        System.out.println("Primitive to Object:");
        System.out.println("Explicit Boxing: " + objA);
        System.out.println("Auto Boxing: " + objAuto);

        // Object to Primitive (Unboxing)
        Integer b = new Integer(200);
        int val1 = b.intValue();  // explicit unboxing
        int val2 = b;             // auto-unboxing

        System.out.println("\nObject to Primitive:");
        System.out.println("Explicit Unboxing: " + val1);
        System.out.println("Auto Unboxing: " + val2);
    }
}
```

---

### 🖥️ **Output:**

```
Primitive to Object:
Explicit Boxing: 100
Auto Boxing: 100

Object to Primitive:
Explicit Unboxing: 200
Auto Unboxing: 200
```

---

### ✅ **Conclusion:**

The program demonstrates how Java's wrapper classes allow seamless conversion between primitive data types and their object equivalents. This is especially helpful when using frameworks or data structures that require objects rather than primitives.
