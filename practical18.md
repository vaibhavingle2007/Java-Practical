### 💡 **Aim:**
Write a program using **Swing** to display a **JComboBox** in a **JFrame**.

---

### 📘 **Theory:**

**JComboBox** is a part of Java’s Swing library and is used to create a drop-down list of options from which a user can select a single value. It’s a convenient way of presenting a list of choices to the user in a compact space.

- **JComboBox** can be populated with data either from an array, a `Vector`, or directly using a `DefaultComboBoxModel`.
- It provides methods like `addItem()`, `getSelectedItem()`, `setSelectedItem()`, etc., to add, retrieve, and modify the list items and the selected item.
- **JFrame** is used to create the main window in which the `JComboBox` will be displayed.

The basic components involved:
- **JFrame**: The main window.
- **JComboBox**: The drop-down list of options.
- **ActionListener**: To handle actions when a selection is made.

---

### 💻 **Program:**

Here’s a simple program to display a **JComboBox** inside a **JFrame**:

```java
import javax.swing.*;  // Importing Swing components
import java.awt.*;  // Importing AWT components
import java.awt.event.*;  // Importing event handling classes

public class JComboBoxExample {

    public static void main(String[] args) {
        // Create a frame (window) to hold the JComboBox
        JFrame frame = new JFrame("JComboBox Example");

        // Create a JComboBox with a list of items (choices)
        String[] fruits = { "Apple", "Banana", "Cherry", "Date", "Elderberry" };
        JComboBox<String> comboBox = new JComboBox<>(fruits);

        // Set the JComboBox properties (optional)
        comboBox.setSelectedIndex(0);  // Set the default selected item (Apple)

        // Create a label to display the selected fruit
        JLabel label = new JLabel("Selected fruit: " + comboBox.getSelectedItem());

        // Add an ActionListener to the JComboBox to update the label when the user selects a fruit
        comboBox.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String selectedFruit = (String) comboBox.getSelectedItem();
                label.setText("Selected fruit: " + selectedFruit);
            }
        });

        // Create a panel to add the JComboBox and label to the frame
        JPanel panel = new JPanel();
        panel.add(comboBox);
        panel.add(label);

        // Add the panel to the frame
        frame.add(panel);

        // Set frame properties
        frame.setSize(300, 150);  // Set size of the window
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);  // Make the window visible
    }
}
```

**Explanation:**
- **JComboBox**: We create a `JComboBox` and pass an array of strings (`fruits`) to it. This array contains the options that will be displayed in the drop-down list.
- **ActionListener**: We add an `ActionListener` to the `JComboBox`. When the user selects an item, the `actionPerformed` method is triggered. It retrieves the selected item using `getSelectedItem()` and updates the `JLabel` to display the selected fruit.
- **JFrame**: We create a `JFrame` to hold the components and set its size and visibility.

---

### 🖥️ **Output:**

When you run the program, a window will appear with a drop-down list containing the fruits: "Apple", "Banana", "Cherry", "Date", and "Elderberry". When the user selects a fruit, the label below the drop-down will update to show the selected fruit. For example, if the user selects "Banana", the label will display:

```
Selected fruit: Banana
```

---

### ✅ **Conclusion:**

This program demonstrates how to use **JComboBox** in **Swing** to create a drop-down list in a GUI application. The use of **ActionListener** allows the program to respond to user interactions, updating the GUI with the selected value from the `JComboBox`. Swing components like `JComboBox` provide an easy way to implement interactive GUI elements in Java applications.
