### 💡 **Aim:**
Write a program to demonstrate the use of **BorderLayout** in Java.

---

### 📘 **Theory:**

**BorderLayout** is one of the most commonly used layout managers in Java AWT. It arranges components in five regions: **North**, **South**, **East**, **West**, and **Center**. Each of these regions can hold only one component, but you can position components in these regions by using the `BorderLayout` manager.

- **North**: Positioned at the top of the container.
- **South**: Positioned at the bottom of the container.
- **East**: Positioned on the right side of the container.
- **West**: Positioned on the left side of the container.
- **Center**: Positioned in the center of the container and takes up all the available space left after placing components in the other regions.

**Syntax for BorderLayout:**
```java
Container.setLayout(new BorderLayout());
```
After setting the layout, you can add components to specific regions using `add()` method with the respective position (e.g., `BorderLayout.NORTH`).

---

### 💻 **Program:**

Here’s a simple program demonstrating the use of **BorderLayout**:

```java
import java.awt.*;  // Importing AWT classes

public class BorderLayoutExample {
    public static void main(String[] args) {
        // Create a frame (window)
        Frame frame = new Frame("BorderLayout Example");

        // Set the layout to BorderLayout
        frame.setLayout(new BorderLayout());

        // Create buttons to add to the frame
        Button button1 = new Button("North");
        Button button2 = new Button("South");
        Button button3 = new Button("East");
        Button button4 = new Button("West");
        Button button5 = new Button("Center");

        // Add the buttons to respective regions in the frame
        frame.add(button1, BorderLayout.NORTH);
        frame.add(button2, BorderLayout.SOUTH);
        frame.add(button3, BorderLayout.EAST);
        frame.add(button4, BorderLayout.WEST);
        frame.add(button5, BorderLayout.CENTER);

        // Set frame size and make it visible
        frame.setSize(400, 300);
        frame.setVisible(true);

        // Close the frame when the close button is clicked
        frame.addWindowListener(new java.awt.event.WindowAdapter() {
            public void windowClosing(java.awt.event.WindowEvent we) {
                System.exit(0);
            }
        });
    }
}
```

**Explanation:**
- A `Frame` object is created to serve as the main window.
- The `BorderLayout` manager is set using `frame.setLayout(new BorderLayout())`.
- Five buttons are created and added to different regions of the frame using the `add()` method with the respective **BorderLayout** constants: `BorderLayout.NORTH`, `BorderLayout.SOUTH`, `BorderLayout.EAST`, `BorderLayout.WEST`, and `BorderLayout.CENTER`.
- The `frame.setSize(400, 300)` sets the size of the window, and `frame.setVisible(true)` makes the window visible.
- The `windowClosing` method ensures that the program terminates when the close button is clicked.

---

### 🖥️ **Output:**

The output will display a window with a button in each of the following positions:
- **North**: "North" button at the top.
- **South**: "South" button at the bottom.
- **East**: "East" button on the right side.
- **West**: "West" button on the left side.
- **Center**: "Center" button in the center of the window.

Each button will occupy the space designated for its region, and the **Center** button will take up the remaining space after the other regions are filled.

---

### ✅ **Conclusion:**

The **BorderLayout** layout manager in Java arranges components in five predefined areas (North, South, East, West, and Center). This layout is useful for creating applications with a clear division of areas for navigation, content display, and interaction. The program demonstrates the usage of **BorderLayout** to arrange buttons in a window, showing how to utilize the layout for different UI components.
