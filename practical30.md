
### 💡 **Aim:**
Write a program to retrieve data from a table using the **`ResultSet`** interface and use various navigation methods.

---

### 📘 **Theory:**

The **`ResultSet`** interface in JDBC represents the result set of a database query. It provides various methods to retrieve data from the database, as well as methods for navigating through the results.

**Navigation Methods of `ResultSet`:**
1. **`next()`**: Moves the cursor to the next row of the result set. It returns **`true`** if there is another row, and **`false`** if there are no more rows.
2. **`previous()`**: Moves the cursor to the previous row in the result set.
3. **`first()`**: Moves the cursor to the first row of the result set.
4. **`last()`**: Moves the cursor to the last row of the result set.
5. **`absolute(int row)`**: Moves the cursor to a specific row number (the index starts at 1).
6. **`relative(int rows)`**: Moves the cursor a specified number of rows relative to its current position.

To retrieve data, the `ResultSet` object provides several **getter methods** like **`getString()`, `getInt()`, `getDouble()`,** etc., to access the data in each column of the current row.

---

### 💻 **Program:**

Here’s a program to retrieve data from a `students` table in a MySQL database and demonstrate navigation using various **`ResultSet`** methods.

#### **Java Code:**

```java
import java.sql.*;

public class ResultSetDemo {

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

            // SQL query to retrieve data from the "students" table
            String selectSQL = "SELECT * FROM students";
            Statement stmt = conn.createStatement(ResultSet.TYPE_SCROLL_INSENSITIVE, ResultSet.CONCUR_READ_ONLY);
            
            // Execute the query and get the result set
            ResultSet rs = stmt.executeQuery(selectSQL);

            // Demonstrating various navigation methods on ResultSet
            
            // Move to the first row and print the data
            if (rs.first()) {
                System.out.println("First Row: ");
                System.out.println("ID: " + rs.getInt(1) + ", Name: " + rs.getString(2) + ", Age: " + rs.getInt(3));
            }

            // Move to the last row and print the data
            if (rs.last()) {
                System.out.println("\nLast Row: ");
                System.out.println("ID: " + rs.getInt(1) + ", Name: " + rs.getString(2) + ", Age: " + rs.getInt(3));
            }

            // Move to the next row and print the data
            if (rs.next()) {
                System.out.println("\nNext Row: ");
                System.out.println("ID: " + rs.getInt(1) + ", Name: " + rs.getString(2) + ", Age: " + rs.getInt(3));
            }

            // Move to the previous row and print the data
            if (rs.previous()) {
                System.out.println("\nPrevious Row: ");
                System.out.println("ID: " + rs.getInt(1) + ", Name: " + rs.getString(2) + ", Age: " + rs.getInt(3));
            }

            // Move to a specific row using absolute
            if (rs.absolute(2)) {
                System.out.println("\nAbsolute Row 2: ");
                System.out.println("ID: " + rs.getInt(1) + ", Name: " + rs.getString(2) + ", Age: " + rs.getInt(3));
            }

            // Close the result set and statement
            rs.close();
            stmt.close();

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

1. **Connection**: The program connects to a MySQL database using JDBC and prepares a **`Statement`** object for executing a query.
   
2. **`ResultSet`**: The `ResultSet` object (`rs`) contains the result of the query execution. It's created with the `ResultSet.TYPE_SCROLL_INSENSITIVE` type, allowing navigation both forward and backward through the result set.

3. **Navigation Methods**:
   - **`rs.first()`**: Moves the cursor to the first row and prints its data.
   - **`rs.last()`**: Moves the cursor to the last row and prints its data.
   - **`rs.next()`**: Moves the cursor to the next row and prints the data.
   - **`rs.previous()`**: Moves the cursor to the previous row and prints its data.
   - **`rs.absolute(2)`**: Moves the cursor to the second row (absolute position) and prints its data.

4. **Closing Resources**: The `ResultSet` and `Statement` are closed to free up database resources, and the connection is also closed in the `finally` block to ensure proper resource management.

---

### 🖥️ **Output:**

Assuming that the `students` table contains multiple records, running the program will produce output similar to the following (values may vary based on the data in your table):

```
First Row: 
ID: 1, Name: John Doe, Age: 22

Last Row: 
ID: 5, Name: Jane Smith, Age: 21

Next Row: 
ID: 2, Name: Mike Johnson, Age: 23

Previous Row: 
ID: 1, Name: John Doe, Age: 22

Absolute Row 2: 
ID: 2, Name: Mike Johnson, Age: 23
```

---

### ✅ **Conclusion:**

This program demonstrates how to retrieve data from a database using **`ResultSet`** and navigate through the result set using various methods:
- **`first()`, `last()`, `next()`, `previous()`, `absolute()`**.
- These methods help in efficiently navigating and retrieving data from the result set based on different needs, like moving to the first, last, next, or a specific row.
