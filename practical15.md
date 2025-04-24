### 💡 **Aim:**
Write a program to create a **menu bar** with various menu items in Java using **AWT**.

---

### 📘 **Theory:**

A **menu bar** in Java provides a way to organize and display menus in a graphical user interface (GUI). The **AWT** library provides a `MenuBar` class to create a menu bar and the `Menu` class to create individual menus.

**Key components:**
- **MenuBar**: This is the container for all the menus.
- **Menu**: Each individual menu (such as File, Edit, etc.).
- **MenuItem**: Represents an item inside a menu.
- **CheckBoxMenuItem**: A type of menu item that allows toggling between checked and unchecked states.
- **RadioButtonMenuItem**: A type of menu item that is part of a mutually exclusive group.

In this example, we will create a menu bar with a few menus like **File** and **Edit**, and demonstrate how to add menu items with action listeners.

---

### 💻 **Program:**

```java
import java.awt.*;  
import java.awt.event.*;

public class MenuBarExample {
    public static void main(String[] args) {
        // Creating a frame (window) to add the menu bar
        Frame frame = new Frame("AWT Menu Bar Example");

        // Create the MenuBar
        MenuBar menuBar = new MenuBar();

        // Create the File Menu
        Menu fileMenu = new Menu("File");
        MenuItem openItem = new MenuItem("Open");
        MenuItem saveItem = new MenuItem("Save");
        fileMenu.add(openItem);
        fileMenu.add(saveItem);

        // Create the Edit Menu
        Menu editMenu = new Menu("Edit");
        MenuItem cutItem = new MenuItem("Cut");
        MenuItem copyItem = new MenuItem("Copy");
        MenuItem pasteItem = new MenuItem("Paste");
        editMenu.add(cutItem);
        editMenu.add(copyItem);
        editMenu.add(pasteItem);

        // Add menus to the menu bar
        menuBar.add(fileMenu);
        menuBar.add(editMenu);

        // Set the menu bar for the frame
        frame.setMenuBar(menuBar);

        // Add action listeners for the menu items
        openItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Open option selected.");
            }
        });

        saveItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Save option selected.");
            }
        });

        cutItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Cut option selected.");
            }
        });

        copyItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Copy option selected.");
            }
        });

        pasteItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Paste option selected.");
            }
        });

        // Frame setup
        frame.setSize(400, 300);
        frame.setVisible(true);

        // Close the frame gracefully
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
    }
}
```

**Explanation:**
- **MenuBar**: We create a `MenuBar` object which will hold all the menus.
- **Menu**: We create two menus: `File` and `Edit`.
- **MenuItem**: Inside the `File` menu, we add two items: "Open" and "Save". Similarly, the `Edit` menu contains "Cut", "Copy", and "Paste".
- **ActionListener**: For each menu item, we attach an `ActionListener` to print a message to the console when the item is selected.
- **Frame**: The menu bar is added to the frame using `frame.setMenuBar(menuBar)`.

---

### 🖥️ **Output:**

When the program runs, a window appears with a menu bar at the top containing:
- **File** menu with **Open** and **Save** options.
- **Edit** menu with **Cut**, **Copy**, and **Paste** options.

When any menu item is clicked, a message is printed in the console indicating which option was selected, for example:

```
Open option selected.
```

---

### ✅ **Conclusion:**

In this program, we have successfully created a **menu bar** with multiple menus and menu items using **AWT** in Java. By attaching `ActionListener` to the menu items, we can trigger specific actions when an item is selected. This demonstrates the basic usage of the **MenuBar**, **Menu**, and **MenuItem** components in AWT for building simple menus in Java desktop applications.
