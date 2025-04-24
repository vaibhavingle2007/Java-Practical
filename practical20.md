### 💡 **Aim:**
Write a program to handle **key events** and **mouse events** in **Java** using **Swing**.

---

### 📘 **Theory:**

- **Key Events**: These are triggered when a user presses or releases a key on the keyboard. In Java, the `KeyListener` interface is used to handle key events. The methods involved are:
  - `keyPressed(KeyEvent e)`: Triggered when a key is pressed.
  - `keyReleased(KeyEvent e)`: Triggered when a key is released.
  - `keyTyped(KeyEvent e)`: Triggered when a key is typed.

- **Mouse Events**: These are triggered when the user interacts with a component using a mouse. Java provides the `MouseListener` interface to handle mouse events. The methods involved are:
  - `mouseClicked(MouseEvent e)`: Triggered when a mouse button is clicked.
  - `mousePressed(MouseEvent e)`: Triggered when a mouse button is pressed.
  - `mouseReleased(MouseEvent e)`: Triggered when a mouse button is released.
  - `mouseEntered(MouseEvent e)`: Triggered when the mouse pointer enters the component.
  - `mouseExited(MouseEvent e)`: Triggered when the mouse pointer exits the component.

---

### 💻 **Program:**

Here’s a Java program that handles both **key events** and **mouse events** using Swing components:

```java
import javax.swing.*;  // Importing Swing components
import java.awt.*;  // Importing AWT components
import java.awt.event.*;  // Importing event handling classes

public class KeyAndMouseEventExample {

    public static void main(String[] args) {
        // Create the JFrame window
        JFrame frame = new JFrame("Key and Mouse Event Example");
        
        // Create a panel to display messages based on events
        JPanel panel = new JPanel();
        panel.setPreferredSize(new Dimension(400, 200));

        // Create a label to show the event info
        JLabel label = new JLabel("Press a key or click the mouse", JLabel.CENTER);
        panel.add(label);

        // Add key listener to the frame to handle key events
        frame.addKeyListener(new KeyAdapter() {
            @Override
            public void keyPressed(KeyEvent e) {
                label.setText("Key Pressed: " + KeyEvent.getKeyText(e.getKeyCode()));
            }

            @Override
            public void keyReleased(KeyEvent e) {
                label.setText("Key Released: " + KeyEvent.getKeyText(e.getKeyCode()));
            }

            @Override
            public void keyTyped(KeyEvent e) {
                label.setText("Key Typed: " + e.getKeyChar());
            }
        });

        // Add mouse listener to the panel to handle mouse events
        panel.addMouseListener(new MouseAdapter() {
            @Override
            public void mouseClicked(MouseEvent e) {
                label.setText("Mouse Clicked at (" + e.getX() + ", " + e.getY() + ")");
            }

            @Override
            public void mousePressed(MouseEvent e) {
                label.setText("Mouse Pressed at (" + e.getX() + ", " + e.getY() + ")");
            }

            @Override
            public void mouseReleased(MouseEvent e) {
                label.setText("Mouse Released at (" + e.getX() + ", " + e.getY() + ")");
            }

            @Override
            public void mouseEntered(MouseEvent e) {
                label.setText("Mouse Entered the panel");
            }

            @Override
            public void mouseExited(MouseEvent e) {
                label.setText("Mouse Exited the panel");
            }
        });

        // Set up the frame to add the panel
        frame.add(panel, BorderLayout.CENTER);
        frame.setSize(400, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
        
        // Make sure the frame is focusable to capture key events
        frame.setFocusable(true);
        frame.requestFocusInWindow();
    }
}
```

**Explanation:**
- **KeyListener**: The program uses `KeyAdapter` to handle the key events. `keyPressed()`, `keyReleased()`, and `keyTyped()` methods update the label text based on the key event.
  - The `keyPressed()` method is triggered when the user presses a key.
  - The `keyReleased()` method is triggered when the user releases a key.
  - The `keyTyped()` method is triggered when the user types a key (usually used for characters).

- **MouseListener**: The program uses `MouseAdapter` to handle mouse events. The methods handle different mouse actions (click, press, release, enter, and exit) and update the label text accordingly.
  - The `mouseClicked()` method is triggered when the user clicks the mouse.
  - The `mousePressed()` method is triggered when the user presses a mouse button.
  - The `mouseReleased()` method is triggered when the user releases a mouse button.
  - The `mouseEntered()` and `mouseExited()` methods are triggered when the mouse enters or exits the panel.

- **Panel**: The `JPanel` is used to capture mouse events. The `JLabel` is used to display the event information in the center.

---

### 🖥️ **Output:**

When you run the program:
- If you press a key, the program will update the label to show the key that was pressed, released, or typed.
- If you click, press, release, enter, or exit the mouse within the panel, the label will update to show the corresponding mouse event along with the coordinates of the mouse (if applicable).

For example:
- After pressing the "A" key:  
  `Key Pressed: A`
- After clicking on the panel:  
  `Mouse Clicked at (100, 150)`

---

### ✅ **Conclusion:**

This program demonstrates how to handle both **key events** and **mouse events** in a **Swing** application. Using `KeyListener` and `MouseListener` interfaces, you can easily capture and respond to user interactions with the keyboard and mouse. This approach is useful for building interactive applications that require real-time user input.
