### 💡 **Aim:**
Write a program to demonstrate various methods of the **`URL`** class and **`URLConnection`** in Java.

---

### 📘 **Theory:**

In Java, the **`URL`** class, part of the **java.net** package, represents a Uniform Resource Locator, which is essentially the address of a resource on the web. The **`URLConnection`** class is used to represent a connection to a resource specified by a **`URL`**.

Common methods of the **`URL`** class include:
- `openConnection()`: Opens a connection to the URL.
- `getHost()`: Retrieves the host name (domain name) of the URL.
- `getPort()`: Retrieves the port number of the URL.
- `getProtocol()`: Retrieves the protocol (e.g., HTTP, FTP) of the URL.
- `getFile()`: Retrieves the file part of the URL (path).
- `getPath()`: Retrieves the path part of the URL.

**`URLConnection`** is used to fetch information about the URL. It allows for reading and writing data from/to a URL and provides methods like:
- `getInputStream()`: Returns an input stream for reading data from the URL.
- `getOutputStream()`: Returns an output stream for writing data to the URL.
- `getContentType()`: Retrieves the content type of the resource.
- `getContentLength()`: Retrieves the length of the content.

---

### 💻 **Program:**

Here’s a Java program demonstrating how to use the **`URL`** and **`URLConnection`** classes:

```java
import java.net.*;  // Importing URL and URLConnection classes
import java.io.*;   // Importing InputStreamReader, BufferedReader classes for reading from URL

public class URLConnectionExample {

    public static void main(String[] args) {
        try {
            // Create a URL object representing the resource
            URL url = new URL("https://www.example.com");

            // Display URL information
            System.out.println("URL: " + url.toString());
            System.out.println("Protocol: " + url.getProtocol());
            System.out.println("Host: " + url.getHost());
            System.out.println("Port: " + url.getPort());
            System.out.println("Path: " + url.getPath());
            System.out.println("File: " + url.getFile());

            // Open a connection to the URL
            URLConnection urlConnection = url.openConnection();
            System.out.println("\nContent-Type: " + urlConnection.getContentType());
            System.out.println("Content-Length: " + urlConnection.getContentLength());

            // Reading content from the URL using InputStream
            try (BufferedReader in = new BufferedReader(new InputStreamReader(urlConnection.getInputStream()))) {
                String inputLine;
                while ((inputLine = in.readLine()) != null) {
                    System.out.println(inputLine);  // Print content line by line
                }
            }

        } catch (MalformedURLException e) {
            System.err.println("Malformed URL: " + e.getMessage());
        } catch (IOException e) {
            System.err.println("IOException: " + e.getMessage());
        }
    }
}
```

**Explanation:**
- **URL object creation**: We create a **`URL`** object representing a website (`https://www.example.com`).
- **Methods of URL**:
  - `getProtocol()`: Returns the protocol used (e.g., HTTP).
  - `getHost()`: Returns the host/domain name.
  - `getPort()`: Returns the port number (if available, or -1 for default).
  - `getPath()`: Returns the path (file location) on the server.
  - `getFile()`: Returns the full file name including the path.
- **URLConnection**: We open a **`URLConnection`** to the specified URL using `url.openConnection()`.
  - `getContentType()`: Returns the content type of the resource (e.g., text/html, application/json).
  - `getContentLength()`: Returns the content length of the resource in bytes.
  - We read the content of the URL using an **InputStreamReader** and **BufferedReader**, printing the content line by line.
  
---

### 🖥️ **Output:**

Running the program will display information about the URL (e.g., the protocol, host, path) and the content from the given URL (`https://www.example.com`), as shown below:

```
URL: https://www.example.com
Protocol: https
Host: www.example.com
Port: -1
Path: /
File: /

Content-Type: text/html; charset=UTF-8
Content-Length: 1256
<html>
<head><title>Example Domain</title></head>
<body>
    <div align="center">
        <h1>Example Domain</h1>
        <p>This domain is established to be used for illustrative examples in documents.</p>
    </div>
</body>
</html>
```

(The actual output will depend on the content available at the URL being accessed.)

---

### ✅ **Conclusion:**

This program demonstrates how to use the **`URL`** and **`URLConnection`** classes to retrieve and manipulate URL-related information in Java. The **`URL`** class allows for parsing and accessing various components of a URL, while the **`URLConnection`** class is useful for accessing and reading data from a remote URL. This is a foundational technique for network programming in Java, especially when working with web resources.
