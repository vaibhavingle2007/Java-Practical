### 💡 **Aim:**
Write a program to:
1. **Create a sample database.**
2. **Make connectivity with the database.**

---

### 📘 **Theory:**

In Java, **JDBC (Java Database Connectivity)** is used to connect to relational databases such as MySQL, Oracle, PostgreSQL, etc. JDBC provides an API for interacting with databases, allowing you to execute SQL queries, update records, retrieve results, and handle database transactions.

Steps to make a database connection:
1. **Load the database driver**: Load the driver specific to the database you're working with (e.g., MySQL).
2. **Establish a connection**: Use **`DriverManager.getConnection()`** to establish a connection to the database using the provided URL, username, and password.
3. **Create a statement**: A **Statement** object is used to send SQL commands to the database.
4. **Execute SQL queries**: Use methods like **`executeQuery()`** to fetch data or **`executeUpdate()`** to modify the database.
5. **Handle exceptions**: JDBC operations should be surrounded by `try-catch` blocks to catch and handle any SQLExceptions.

---

### 💻 **Program:**

Here’s an example of a program that:
1. **Creates a sample database** called `testdb`.
2. **Makes a connection** to the database.
3. **Creates a sample table**.
4. **Inserts some data** into the table.

#### **JDBC Program to Create a Sample Database and Make Connectivity:**

**Step 1:** Make sure you have the **JDBC driver** for the database you're using (e.g., MySQL JDBC driver). You need to add the driver to your classpath.

#### **Java Code:**

```java
import java.sql.*;

public class DatabaseConnectivity {

    public static void main(String[] args) {
        // JDBC URL, username, and password for MySQL
        String url = "jdbc:mysql://localhost:3306/";
        String user = "root";
        String password = "yourpassword"; // Replace with your MySQL password
        
        // JDBC connection object
        Connection conn = null;

        try {
            // Load the MySQL JDBC driver (optional for newer versions of JDBC)
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish connection to MySQL server
            conn = DriverManager.getConnection(url, user, password);
            
            // Create statement object to send SQL commands to the database
            Statement stmt = conn.createStatement();
            
            // Create the database "testdb"
            String createDbSQL = "CREATE DATABASE IF NOT EXISTS testdb";
            stmt.executeUpdate(createDbSQL);
            System.out.println("Database 'testdb' created successfully!");

            // Switch to the created database
            conn.setCatalog("testdb");

            // Create a table "students"
            String createTableSQL = "CREATE TABLE IF NOT EXISTS students ("
                    + "id INT AUTO_INCREMENT PRIMARY KEY, "
                    + "name VARCHAR(100), "
                    + "age INT)";
            stmt.executeUpdate(createTableSQL);
            System.out.println("Table 'students' created successfully!");

            // Insert sample data into the "students" table
            String insertSQL = "INSERT INTO students (name, age) VALUES "
                    + "('John Doe', 20), "
                    + "('Jane Smith', 22), "
                    + "('Emily Johnson', 21)";
            stmt.executeUpdate(insertSQL);
            System.out.println("Sample data inserted into 'students' table!");

            // Retrieve data from the "students" table
            String selectSQL = "SELECT * FROM students";
            ResultSet rs = stmt.executeQuery(selectSQL);

            // Display retrieved data
            System.out.println("Student Data:");
            while (rs.next()) {
                int id = rs.getInt("id");
                String name = rs.getString("name");
                int age = rs.getInt("age");
                System.out.println(id + ": " + name + ", " + age + " years old");
            }
            
            // Close the ResultSet and Statement objects
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

1. **Database URL**: The connection URL is `jdbc:mysql://localhost:3306/` for MySQL, where `3306` is the default port for MySQL.
2. **`Class.forName("com.mysql.cj.jdbc.Driver")`**: This loads the MySQL JDBC driver.
3. **`DriverManager.getConnection()`**: This method establishes a connection to the MySQL server.
4. **Creating a database**: The SQL command `CREATE DATABASE IF NOT EXISTS testdb` ensures that the database is created if it doesn't exist.
5. **Switch to the database**: The connection's catalog is set to the `testdb` database using `conn.setCatalog("testdb")`.
6. **Creating a table**: The SQL command creates a table called `students` with columns `id`, `name`, and `age`.
7. **Inserting data**: Sample data is inserted into the `students` table.
8. **Selecting and displaying data**: The `SELECT` statement retrieves all records from the `students` table, and the program displays them.

---

### 🖥️ **Output:**

When you run the program, you should see the following output:

```
Database 'testdb' created successfully!
Table 'students' created successfully!
Sample data inserted into 'students' table!
Student Data:
1: John Doe, 20 years old
2: Jane Smith, 22 years old
3: Emily Johnson, 21 years old
```

---

### ✅ **Conclusion:**

This program demonstrates how to:
1. **Create a database** (`testdb`).
2. **Establish a connection** with the database.
3. **Create a table** (`students`).
4. **Insert sample data** into the table.
5. **Retrieve and display the data** from the table.

The use of JDBC enables Java applications to interact with databases, and this is fundamental for database-driven applications. By adjusting the connection URL and credentials, you can connect to different types of databases like MySQL, PostgreSQL, etc.
