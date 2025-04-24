### 💡 **Aim:**
Write a program to handle **text events** on **Swing** components in Java.

---

### 📘 **Theory:**

In Java, **Text Events** occur when a user interacts with a text-based component such as a **JTextField**, **JTextArea**, or **JPasswordField**. These events include actions like typing, editing, or changing text.

The **TextListener** interface is used to handle **Text Events**. The main method to handle these events is `textValueChanged()`. A **TextListener** can be added to text components like **JTextField**, **JTextArea**, etc., to listen for text changes.

Common scenarios for using **TextEvents** include:
- Monitoring user input in a text field.
- Updating other parts of the UI based on text input.
- Performing validation as text is entered.

---

### 💻 **Program:**

Here’s a Java program that demonstrates how to handle **text events** on a **JTextField** component using **TextListener**:

```java
import javax.swing.*;  // Importing Swing components
import java.awt.*;  // Importing AWT components
import java.awt.event.*;  // Importing event handling classes

public class TextEventExample {

    public static void main(String[] args) {
        // Create the JFrame (window)
        JFrame frame = new JFrame("Text Event Example");

        // Create a JTextField for user input
        JTextField textField = new JTextField(20);

        // Create a JLabel to display the text entered
        JLabel label = new JLabel("Enter text in the field", JLabel.CENTER);

        // Add a TextListener to the JTextField to handle text changes
        textField.addTextListener(new TextListener() {
            @Override
            public void textValueChanged(TextEvent e) {
                // Get the text entered in the JTextField and set it in the label
                label.setText("Text Entered: " + textField.getText());
            }
        });

        // Create a JPanel to hold the components
        JPanel panel = new JPanel();
        panel.setLayout(new FlowLayout());
        panel.add(textField);  // Add the text field to the panel
        panel.add(label);      // Add the label to the panel

        // Set up the frame
        frame.add(panel);
        frame.setSize(400, 150);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

**Explanation:**
- **JTextField**: We use a `JTextField` for user input. This component allows users to type text into the field.
- **JLabel**: A `JLabel` is used to display the entered text dynamically.
- **TextListener**: The `TextListener` interface listens for changes in the text value of the `JTextField`. The method `textValueChanged()` is invoked every time the user types in the text field.
  - Inside `textValueChanged()`, we retrieve the text from the `JTextField` and update the `JLabel` to show the current entered text.
- **Layout and Components**: We place the `JTextField` and `JLabel` in a `FlowLayout` inside a `JPanel`, and then add the panel to the frame.

---

### 🖥️ **Output:**

When you run the program:
- A window with a **JTextField** and a **JLabel** appears.
- As the user types in the **JTextField**, the **JLabel** dynamically updates to show the entered text.

For example:
- If the user types "Hello", the label will update to:  
  `"Text Entered: Hello"`

---

### ✅ **Conclusion:**

This program demonstrates how to handle **text events** using the **TextListener** interface in a **Swing** application. By listening for changes in text input, we can react to user input in real-time, which is useful for implementing features like live validation, form updates, or instant feedback in Java-based GUI applications.
