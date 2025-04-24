### 💡 **Aim:**
Write a program to implement an **ActionEvent** in a **frame** using **Swing** components.

---

### 📘 **Theory:**

In Java, **ActionEvent** is generated when an action is performed by the user, such as pressing a button, selecting a menu item, or selecting an item from a list. The **ActionEvent** is an essential part of **Swing** programming, which is used to perform actions based on user interactions.

To handle an **ActionEvent**, you need to:
- Use an **ActionListener** to listen for events.
- Attach the **ActionListener** to the component (like a button, text field, etc.).
- Handle the action event in the `actionPerformed()` method of the **ActionListener**.

In the context of Swing, **JButton**, **JTextField**, and other components can trigger **ActionEvent**.

---

### 💻 **Program:**

Here’s a Java program that demonstrates how to implement **ActionEvent** using a **JButton** in a **JFrame**:

```java
import javax.swing.*;  // Importing Swing components
import java.awt.*;  // Importing AWT components
import java.awt.event.*;  // Importing event handling classes

public class ActionEventExample {

    public static void main(String[] args) {
        // Create a JFrame (window)
        JFrame frame = new JFrame("Action Event Example");

        // Create a JButton component
        JButton button = new JButton("Click Me");

        // Create a JLabel to display messages
        JLabel label = new JLabel("Press the button to see the action.", JLabel.CENTER);

        // Create an ActionListener to handle the action event
        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                // Change the text of the label when the button is clicked
                label.setText("Button Clicked!");
            }
        });

        // Set the layout of the frame
        frame.setLayout(new BorderLayout());
        frame.add(button, BorderLayout.SOUTH);  // Add the button to the bottom of the frame
        frame.add(label, BorderLayout.CENTER);  // Add the label to the center of the frame

        // Set the frame properties
        frame.setSize(400, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

**Explanation:**
- **JButton**: We create a `JButton` labeled `"Click Me"`. This button will trigger an **ActionEvent** when clicked.
- **JLabel**: We use a `JLabel` to display messages that will change when the button is clicked.
- **ActionListener**: An **ActionListener** is added to the button to listen for **ActionEvent**. When the button is clicked, the `actionPerformed()` method is invoked, which changes the text of the label to `"Button Clicked!"`.
- **Frame Layout**: The frame uses a `BorderLayout`. The button is placed at the bottom (South) and the label in the center of the frame.
- **Visibility and Frame Settings**: The frame size is set to 400x200 pixels, and the frame is set to close when the user exits.

---

### 🖥️ **Output:**

When you run the program, a window will appear with a **JButton** labeled `"Click Me"`. Initially, a **JLabel** displays `"Press the button to see the action."`.

- When the user clicks the button, the label’s text will change to:  
  `"Button Clicked!"`

---

### ✅ **Conclusion:**

This program demonstrates how to use **ActionEvent** in a **Swing** application. By adding an **ActionListener** to the **JButton**, we can handle the button click and perform an action (in this case, changing the text of a label). This is a fundamental approach to creating interactive GUI applications in Java using **Swing**.
