### 💡 **Aim:**
Write a program to design a **calculator** to demonstrate **GridLayout** using **Swing** components in Java.

---

### 📘 **Theory:**

**Swing** is a part of the Java Foundation Classes (JFC) that provides a set of GUI components for building rich user interfaces. Unlike AWT, Swing provides more advanced components such as `JButton`, `JTextField`, and `JPanel`.

**GridLayout** is a layout manager in Java that arranges components in a grid of rows and columns. It ensures that all components have equal size and are distributed across the grid. The components are added from left to right, row by row.

**Key components used for the calculator:**
- **JButton**: Represents each button in the calculator (e.g., digits, operations, and the equal sign).
- **JTextField**: Used for displaying the input and result.
- **JFrame**: The window frame that holds all the components.

**GridLayout** is particularly useful for the calculator because it allows for the equal distribution of buttons across the grid.

---

### 💻 **Program:**

Here’s a simple calculator program using **Swing** components and **GridLayout**:

```java
import javax.swing.*;  // Importing Swing components
import java.awt.*;  // Importing AWT components
import java.awt.event.*;  // Importing event handling classes

public class CalculatorExample {

    // Method to evaluate the mathematical expression
    public static double evaluateExpression(String expression) {
        // For simplicity, we are directly using eval() via JavaScript (not recommended for production)
        try {
            return (double) new javax.script.ScriptEngineManager().getEngineByName("JavaScript").eval(expression);
        } catch (Exception e) {
            return 0;
        }
    }

    public static void main(String[] args) {
        // Create the frame (main window) and set its title
        JFrame frame = new JFrame("Calculator");

        // Create the text field to display the input and output
        JTextField textField = new JTextField();

        // Create the panel with GridLayout (4 rows, 4 columns)
        JPanel panel = new JPanel(new GridLayout(4, 4));

        // Buttons for numbers and operations
        String[] buttons = {
            "7", "8", "9", "/",
            "4", "5", "6", "*",
            "1", "2", "3", "-",
            "0", ".", "=", "+"
        };

        // StringBuilder to store the input expression
        StringBuilder expression = new StringBuilder();

        // Action listener for handling button clicks
        ActionListener buttonClickListener = new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String command = e.getActionCommand();

                // If "=" is clicked, evaluate the expression
                if (command.equals("=")) {
                    try {
                        double result = evaluateExpression(expression.toString());
                        textField.setText(String.valueOf(result));
                        expression.setLength(0);  // Clear the expression
                    } catch (Exception ex) {
                        textField.setText("Error");
                    }
                } else {
                    // Append the clicked button's text to the expression
                    expression.append(command);
                    textField.setText(expression.toString());
                }
            }
        };

        // Add buttons to the panel and set their action commands
        for (String text : buttons) {
            JButton button = new JButton(text);
            button.addActionListener(buttonClickListener);
            panel.add(button);
        }

        // Add the text field and panel to the frame
        frame.add(textField, BorderLayout.NORTH);
        frame.add(panel, BorderLayout.CENTER);

        // Configure the frame (size, close operation, visibility)
        frame.setSize(400, 400);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

**Explanation:**
- **JTextField**: The text field is used to display the input and the result of calculations.
- **GridLayout**: The panel uses `GridLayout(4, 4)` to arrange the calculator buttons in 4 rows and 4 columns.
- **JButton**: Each button is created and added to the panel with a corresponding action listener.
- **ActionListener**: When a button is clicked, it either appends the button’s text to the current expression or evaluates the expression if the "=" button is clicked.
- **JavaScript Engine**: For simplicity, we are using Java's built-in `ScriptEngineManager` to evaluate the expression as a JavaScript expression (note that this is not recommended for production code).

---

### 🖥️ **Output:**

When you run the program, a calculator window will appear with buttons for digits, decimal points, and basic arithmetic operations (+, -, *, /). The top text field will display the expression, and once the user clicks the "=" button, the result will be displayed.

---

### ✅ **Conclusion:**

This program demonstrates how to use **GridLayout** in combination with **Swing** components to create a simple calculator GUI. The **GridLayout** manager is ideal for this type of task as it ensures that the calculator buttons are evenly distributed in a grid format. The program also shows how to handle basic arithmetic operations and evaluate expressions using a **JTextField** for displaying the result.
