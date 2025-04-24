### 💡 **Aim:**
Write a program to retrieve the **hostname** and **IP address** using the **`InetAddress`** class.

---

### 📘 **Theory:**

In Java, the **`InetAddress`** class is part of the **java.net** package and is used to represent an IP address (both IPv4 and IPv6). This class provides methods to resolve hostnames to IP addresses and vice versa. Common methods of the **`InetAddress`** class include:
- `getByName(String host)`: Resolves the hostname to an IP address.
- `getHostName()`: Retrieves the hostname of the machine.
- `getHostAddress()`: Retrieves the IP address of the machine.
- `getLocalHost()`: Returns the local host's **InetAddress** (this typically refers to the machine running the code).

The **`InetAddress`** class is typically used for network-related tasks such as identifying the local machine or resolving remote hostnames to IP addresses.

---

### 💻 **Program:**

Here’s a Java program to retrieve the **hostname** and **IP address** of the local machine using the **`InetAddress`** class:

```java
import java.net.*;  // Importing the InetAddress class for network operations

public class HostInfo {

    public static void main(String[] args) {
        try {
            // Retrieve the InetAddress object for the local machine
            InetAddress inetAddress = InetAddress.getLocalHost();
            
            // Get the hostname and IP address
            String hostname = inetAddress.getHostName();  // Get the hostname of the machine
            String ipAddress = inetAddress.getHostAddress();  // Get the IP address of the machine
            
            // Display the results
            System.out.println("Hostname: " + hostname);
            System.out.println("IP Address: " + ipAddress);
        } catch (UnknownHostException e) {
            // Handle the exception if the host could not be determined
            System.err.println("Error retrieving host information: " + e.getMessage());
        }
    }
}
```

**Explanation:**
- **InetAddress.getLocalHost()**: This method retrieves the `InetAddress` object for the local machine (the computer on which the program is running).
- **getHostName()**: This method retrieves the hostname (computer name) of the local machine.
- **getHostAddress()**: This method retrieves the IP address of the local machine in string format (e.g., "192.168.1.1").
- **UnknownHostException**: This exception is caught in case the hostname or IP address could not be determined (e.g., network issues or invalid local address).

---

### 🖥️ **Output:**

When you run the program, you will see the output similar to the following:

```
Hostname: your-computer-name
IP Address: 192.168.1.2
```

The **hostname** and **IP address** will vary based on your local machine and network configuration.

---

### ✅ **Conclusion:**

This program demonstrates how to use the **`InetAddress`** class in Java to retrieve the **hostname** and **IP address** of the local machine. This is useful for network programming, system diagnostics, and applications that require network configuration or identification.
