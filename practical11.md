### 💡 **Aim:**
Write programs using **Multithreading** in Java.

---

### 📘 **Theory:**

**Multithreading** in Java is a process of executing multiple threads concurrently. A thread is a lightweight process that has its own execution path. Java allows for **multithreading** to achieve better resource utilization, especially in tasks that are independent of each other.

**Key points about Multithreading in Java:**
- Every Java application has at least one thread, which is the **main thread**.
- Multithreading can be implemented by either:
  1. Extending the `Thread` class and overriding its `run()` method.
  2. Implementing the `Runnable` interface and overriding its `run()` method.
- Threads can be managed using methods like `start()`, `sleep()`, `join()`, and `interrupt()`.

---

### 💻 **Program:**

**1. Example using Thread class:**

```java
// Extending the Thread class
class MyThread extends Thread {
    public void run() {
        // Code that runs in the thread
        for (int i = 1; i <= 5; i++) {
            System.out.println(Thread.currentThread().getId() + " Value: " + i);
            try {
                Thread.sleep(500); // Sleep for 500 milliseconds
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

public class ThreadExample {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();
        
        t1.start();  // Starting the first thread
        t2.start();  // Starting the second thread
    }
}
```

**Explanation:**
- In this example, the `MyThread` class extends the `Thread` class and overrides the `run()` method to specify the code that will be executed in the thread.
- Two threads `t1` and `t2` are created and started using `start()`.

---

**2. Example using Runnable interface:**

```java
// Implementing the Runnable interface
class MyRunnable implements Runnable {
    public void run() {
        // Code that runs in the thread
        for (int i = 1; i <= 5; i++) {
            System.out.println(Thread.currentThread().getId() + " Value: " + i);
            try {
                Thread.sleep(500); // Sleep for 500 milliseconds
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

public class RunnableExample {
    public static void main(String[] args) {
        MyRunnable runnable = new MyRunnable();
        
        // Creating Thread objects with the Runnable object
        Thread t1 = new Thread(runnable);
        Thread t2 = new Thread(runnable);
        
        t1.start();  // Starting the first thread
        t2.start();  // Starting the second thread
    }
}
```

**Explanation:**
- In this example, the `MyRunnable` class implements the `Runnable` interface and overrides the `run()` method to specify the code for execution.
- Two `Thread` objects (`t1` and `t2`) are created using the `Runnable` object, and then the threads are started using `start()`.

---

### 🖥️ **Output:**

**Output for Thread class:**

```
1 Value: 1
1 Value: 2
1 Value: 3
1 Value: 4
1 Value: 5
2 Value: 1
2 Value: 2
2 Value: 3
2 Value: 4
2 Value: 5
```

**Output for Runnable interface:**

```
1 Value: 1
1 Value: 2
1 Value: 3
1 Value: 4
1 Value: 5
2 Value: 1
2 Value: 2
2 Value: 3
2 Value: 4
2 Value: 5
```

*Note: The order in which the threads execute may vary each time you run the program.*

---

### ✅ **Conclusion:**

This program demonstrates **Multithreading** in Java using two approaches:
1. Extending the `Thread` class.
2. Implementing the `Runnable` interface.

Multithreading allows multiple threads to run concurrently, enabling efficient use of system resources and better performance for tasks that can be performed independently. Both approaches are valid for creating threads, but using `Runnable` is preferred when you need to extend another class as well.
