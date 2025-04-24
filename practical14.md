### 💡 **Aim:**
Write a program to design any type of form using **AWT** (Abstract Window Toolkit) in Java.

---

### 📘 **Theory:**

**AWT (Abstract Window Toolkit)** is a set of Java classes used for creating graphical user interfaces (GUIs). AWT provides a collection of components (like buttons, text fields, labels, etc.) and layouts for building windows-based applications.

**Key components of AWT:**
- **Frame**: A window with title and borders.
- **Button**: A clickable button.
- **TextField**: A single-line text input field.
- **Label**: A non-editable text element.
- **Checkbox**: A box that can be checked or unchecked.
- **Choice**: A dropdown menu.
- **Panel**: A container for organizing components.

AWT is part of Java’s GUI libraries but has been largely replaced by **Swing** for more advanced and flexible UI elements. However, it is still useful for basic form-based applications.

---

### 💻 **Program:**

Here’s a simple example of a **Form Design** using AWT components like `TextField`, `Label`, `Button`, and `Checkbox`.

```java
import java.awt.*;  // Importing AWT classes
import java.awt.event.*;  // Importing event handling classes

public class AWTFormExample {
    public static void main(String[] args) {
        // Create a frame (window)
        Frame frame = new Frame("AWT Form Example");

        // Create labels, textfields, and button
        Label nameLabel = new Label("Enter your name:");
        TextField nameField = new TextField();
        
        Label ageLabel = new Label("Enter your age:");
        TextField ageField = new TextField();
        
        Button submitButton = new Button("Submit");

        // Set layout for the frame
        frame.setLayout(new FlowLayout());

        // Add components to the frame
        frame.add(nameLabel);
        frame.add(nameField);
        frame.add(ageLabel);
        frame.add(ageField);
        frame.add(submitButton);

        // Handle the button click event
        submitButton.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String name = nameField.getText();
                String age = ageField.getText();
                System.out.println("Name: " + name);
                System.out.println("Age: " + age);
            }
        });

        // Set frame size and visibility
        frame.setSize(300, 200);
        frame.setVisible(true);

        // Close the frame when the close button is clicked
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);  // Terminate the program
            }
        });
    }
}
```

**Explanation:**
- We create a `Frame` object (a window) for the form.
- Inside the frame, we add `Label` components for showing text, `TextField` components for user input, and a `Button` to submit the form.
- We use the `FlowLayout` to arrange the components in the window, making them appear in a sequential manner.
- The `submitButton.addActionListener` listens for a button click, and upon clicking, it retrieves the text entered in the name and age fields and prints it to the console.
- `WindowAdapter` is used to close the frame gracefully when the close button is clicked.

---

### 🖥️ **Output:**

Upon running the program, you will get a simple form with the following:
- Text fields for name and age input.
- A submit button to print the entered data.

Here’s a visual representation of the form:
- **Enter your name**: (TextField to input name)
- **Enter your age**: (TextField to input age)
- **Submit**: (Button to submit the data)

When the user clicks the **Submit** button, the entered data is printed in the console:

```
Name: Vaibhav
Age: 25
```

---

### ✅ **Conclusion:**

This program demonstrates the use of AWT to create a simple form with text fields and a button. AWT provides basic components like `Label`, `TextField`, and `Button` that allow you to create functional forms. Though more advanced UI frameworks like **Swing** and **JavaFX** are commonly used for more complex applications, AWT still provides a straightforward way to build simple GUI forms.
