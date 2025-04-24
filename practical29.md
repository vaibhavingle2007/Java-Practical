
### 💡 **Aim:**
Write a program to demonstrate the use of **`PreparedStatement`**.

---

### 📘 **Theory:**

In JDBC, the **`PreparedStatement`** class is an extension of the **`Statement`** class, and it is used to execute SQL queries that are precompiled and stored in the database. The main advantage of **`PreparedStatement`** over **`Statement`** is that it can be reused with different values for the same SQL query. It is also more efficient because the SQL query is precompiled, reducing the overhead of compiling the query every time it is executed.

**Key Features of `PreparedStatement`:**
- It helps in executing **parameterized SQL queries**.
- It provides better performance as the query is precompiled.
- It helps to prevent **SQL injection** attacks because the input parameters are not directly concatenated into the SQL string.

The syntax for using **`PreparedStatement`**:
- **`PreparedStatement pstmt = connection.prepareStatement(query);`**
- You can set parameters in the query using **`pstmt.setXXX(index, value)`**, where **`index`** refers to the position of the placeholder (`?`) and **`value`** is the value to be inserted.
- For example: **`pstmt.setString(1, "John")`** sets the first parameter to "John".

---

### 💻 **Program:**

Here’s a Java program demonstrating the use of **`PreparedStatement`** to **insert**, **update**, and **delete** records from a `students` table.

#### **Java Code:**

```java
import java.sql.*;

public class PreparedStatementDemo {

    public static void main(String[] args) {
        // JDBC URL, username, and password for MySQL
        String url = "jdbc:mysql://localhost:3306/testdb";  // Database name is testdb
        String user = "root";
        String password = "yourpassword"; // Replace with your MySQL password
        
        // JDBC connection object
        Connection conn = null;

        try {
            // Load the MySQL JDBC driver (optional for newer versions of JDBC)
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish connection to the MySQL database
            conn = DriverManager.getConnection(url, user, password);

            // 1. Using PreparedStatement to insert a record into the "students" table
            String insertSQL = "INSERT INTO students (name, age) VALUES (?, ?)";
            PreparedStatement pstmtInsert = conn.prepareStatement(insertSQL);
            pstmtInsert.setString(1, "John Doe");
            pstmtInsert.setInt(2, 22);
            pstmtInsert.executeUpdate();
            System.out.println("Record inserted successfully!");

            // 2. Using PreparedStatement to update a record in the "students" table
            String updateSQL = "UPDATE students SET age = ? WHERE name = ?";
            PreparedStatement pstmtUpdate = conn.prepareStatement(updateSQL);
            pstmtUpdate.setInt(1, 23);
            pstmtUpdate.setString(2, "John Doe");
            pstmtUpdate.executeUpdate();
            System.out.println("Record updated successfully!");

            // 3. Using PreparedStatement to delete a record from the "students" table
            String deleteSQL = "DELETE FROM students WHERE name = ?";
            PreparedStatement pstmtDelete = conn.prepareStatement(deleteSQL);
            pstmtDelete.setString(1, "John Doe");
            pstmtDelete.executeUpdate();
            System.out.println("Record deleted successfully!");

        } catch (SQLException | ClassNotFoundException e) {
            System.err.println("Database error: " + e.getMessage());
        } finally {
            // Close the database connection
            if (conn != null) {
                try {
                    conn.close();
                } catch (SQLException e) {
                    System.err.println("Error closing connection: " + e.getMessage());
                }
            }
        }
    }
}
```

---

### **Explanation:**

1. **Insert using `PreparedStatement`**:
   - The SQL query `INSERT INTO students (name, age) VALUES (?, ?)` contains placeholders (`?`), and we use **`pstmt.setString(1, "John Doe")`** and **`pstmt.setInt(2, 22)`** to insert the values at the specified positions in the query.
   
2. **Update using `PreparedStatement`**:
   - The SQL query `UPDATE students SET age = ? WHERE name = ?` updates the age of a student with a specified name. **`pstmt.setInt(1, 23)`** updates the age to 23 for "John Doe".
   
3. **Delete using `PreparedStatement`**:
   - The SQL query `DELETE FROM students WHERE name = ?` deletes the record where the name is "John Doe". **`pstmt.setString(1, "John Doe")`** is used to specify the name of the student to be deleted.

---

### 🖥️ **Output:**

When you run the program, you should see the following output:

```
Record inserted successfully!
Record updated successfully!
Record deleted successfully!
```

This output indicates that:
1. The **insert** operation was successful.
2. The **update** operation was successful.
3. The **delete** operation was successful.

---

### ✅ **Conclusion:**

This program demonstrates how to use **`PreparedStatement`** to perform **insert**, **update**, and **delete** operations in a database. By using **`PreparedStatement`**, you can:
- Execute parameterized SQL queries, which is safer and more efficient.
- Prevent SQL injection attacks by separating SQL code from input data.
- Improve performance by pre-compiling SQL queries.
