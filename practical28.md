
### 💡 **Aim:**
Write a program to implement the following operations on the database:
1. **Insert record.**
2. **Update record.**
3. **Delete record.**

---

### 📘 **Theory:**

In JDBC, **SQL Operations** like **INSERT**, **UPDATE**, and **DELETE** are performed using the **`executeUpdate()`** method of the **`Statement`** or **`PreparedStatement`** class. These operations modify the data in the database and are used for:
- **INSERT**: To add new records into a table.
- **UPDATE**: To modify existing records in a table.
- **DELETE**: To remove records from a table.

### Steps:
1. **Insert Record**: You can insert data into a table by providing the values for each column in the table.
2. **Update Record**: You modify the values of existing records based on certain conditions (e.g., updating a user's name).
3. **Delete Record**: This operation removes records that meet certain conditions (e.g., deleting a user with a specific ID).

---

### 💻 **Program:**

Here’s a program that demonstrates **INSERT**, **UPDATE**, and **DELETE** operations on a **students** table in a MySQL database.

#### **Java Code:**

```java
import java.sql.*;

public class DatabaseOperations {

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

            // Create statement object to send SQL commands to the database
            Statement stmt = conn.createStatement();

            // 1. Insert record into the "students" table
            String insertSQL = "INSERT INTO students (name, age) VALUES ('Michael Scott', 30)";
            stmt.executeUpdate(insertSQL);
            System.out.println("Record inserted successfully!");

            // 2. Update record in the "students" table
            String updateSQL = "UPDATE students SET age = 25 WHERE name = 'Michael Scott'";
            stmt.executeUpdate(updateSQL);
            System.out.println("Record updated successfully!");

            // 3. Delete record from the "students" table
            String deleteSQL = "DELETE FROM students WHERE name = 'Michael Scott'";
            stmt.executeUpdate(deleteSQL);
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

1. **Insert Record**:
   - The SQL query `INSERT INTO students (name, age) VALUES ('Michael Scott', 30)` adds a new record with the name "Michael Scott" and age 30 to the `students` table.
   
2. **Update Record**:
   - The SQL query `UPDATE students SET age = 25 WHERE name = 'Michael Scott'` modifies the age of the student named "Michael Scott" to 25.
   
3. **Delete Record**:
   - The SQL query `DELETE FROM students WHERE name = 'Michael Scott'` removes the record for the student named "Michael Scott" from the `students` table.

---

### 🖥️ **Output:**

When you run the program, the following output will be displayed:

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

This program demonstrates how to:
1. **Insert** a new record into the database using the `INSERT` statement.
2. **Update** an existing record in the database using the `UPDATE` statement.
3. **Delete** a record from the database using the `DELETE` statement.

JDBC enables Java applications to interact with relational databases and perform data manipulation operations like inserting, updating, and deleting records.
