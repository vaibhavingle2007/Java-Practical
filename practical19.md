### 💡 **Aim:**
Write a program to create a **JTree** and **JTable** in **Java** using **Swing**.

---

### 📘 **Theory:**

- **JTree**: The `JTree` class in Java is used to display a hierarchical tree of data. The tree consists of **nodes**, and each node can have child nodes. It is useful for displaying data that has a parent-child relationship.
    - `DefaultMutableTreeNode`: A commonly used class to create tree nodes.
    - Methods: `add()`, `setRoot()`, `getChildCount()`, and others for manipulating tree nodes.

- **JTable**: The `JTable` class in Java is used to display data in a table format. It is one of the most widely used components for displaying data in grid form, where rows represent records and columns represent attributes.
    - JTable can be populated using `TableModel` to store and display tabular data.
    - It allows customization of columns, rows, and how data is presented (e.g., editable cells).

Both `JTree` and `JTable` are essential components in creating rich, interactive Java GUI applications.

---

### 💻 **Program:**

Here’s a program that demonstrates the creation of both a **JTree** and a **JTable** in a **JFrame**:

```java
import javax.swing.*;  // Importing Swing components
import javax.swing.tree.*;  // Importing JTree classes
import javax.swing.table.DefaultTableModel;  // Importing Table model
import java.awt.*;  // Importing AWT components

public class JTreeAndJTableExample {

    public static void main(String[] args) {
        // Create the JFrame window
        JFrame frame = new JFrame("JTree and JTable Example");

        // Create a JTree with a root and child nodes
        DefaultMutableTreeNode rootNode = new DefaultMutableTreeNode("Root");
        DefaultMutableTreeNode node1 = new DefaultMutableTreeNode("Node 1");
        DefaultMutableTreeNode node2 = new DefaultMutableTreeNode("Node 2");
        rootNode.add(node1);
        rootNode.add(node2);

        // Create the JTree with the root node
        JTree tree = new JTree(rootNode);
        JScrollPane treeScrollPane = new JScrollPane(tree);  // Adding the tree to a scroll pane

        // Create the JTable with some sample data
        String[] columns = {"ID", "Name", "Age"};
        Object[][] data = {
            {1, "John", 25},
            {2, "Sara", 30},
            {3, "Mike", 35}
        };

        // Create a table model for the JTable
        DefaultTableModel tableModel = new DefaultTableModel(data, columns);
        JTable table = new JTable(tableModel);
        JScrollPane tableScrollPane = new JScrollPane(table);  // Adding the table to a scroll pane

        // Create a panel for adding the tree and table
        JPanel panel = new JPanel();
        panel.setLayout(new GridLayout(1, 2));  // Arrange tree and table side by side
        panel.add(treeScrollPane);
        panel.add(tableScrollPane);

        // Add the panel to the frame
        frame.add(panel);

        // Set frame properties
        frame.setSize(600, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

**Explanation:**
- **JTree**: We create a `JTree` object, starting with a root node (`"Root"`) and two child nodes (`"Node 1"` and `"Node 2"`). These nodes are added to a `DefaultMutableTreeNode`, which is then used to construct the `JTree`.
- **JTable**: A `DefaultTableModel` is used to hold the data in a table format. We define a simple table with columns `"ID"`, `"Name"`, and `"Age"`, and provide some sample data. The `JTable` is then created using this model.
- **Layout**: The `JTree` and `JTable` are placed side by side using a `GridLayout(1, 2)` in a panel. Both components are wrapped in `JScrollPane` to allow scrolling.
- **JFrame**: The main frame contains the panel with the tree and table, and is set to be visible.

---

### 🖥️ **Output:**

When you run the program, a window will appear with two sections:
1. On the left, a **JTree** displaying a hierarchical structure with a root node and two child nodes.
2. On the right, a **JTable** displaying data in a tabular format with columns `"ID"`, `"Name"`, and `"Age"`, and rows containing sample data.

---

### ✅ **Conclusion:**

This program demonstrates the use of **JTree** and **JTable** in a single Java GUI application. **JTree** is used to display hierarchical data, and **JTable** is used to display tabular data. Both components are enclosed in **JScrollPane** to ensure that users can scroll if the content exceeds the visible area. This type of setup is useful when you need to display both hierarchical and tabular data in the same interface.
