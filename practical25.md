### 💡 **Aim:**
Write a program that demonstrates **connection-oriented communication** using a **Socket** in Java.

---

### 📘 **Theory:**

In **Java**, connection-oriented communication is typically implemented using **TCP (Transmission Control Protocol)**, which ensures reliable, ordered, and error-checked delivery of data between applications running on different devices.

The **`Socket`** class is used to create a client-side socket for communication with a server. A **`ServerSocket`** is used to create a server-side socket that listens for incoming connections from clients.

The basic steps involved in connection-oriented communication are:
1. **Server-side**:
   - A **`ServerSocket`** listens on a specific port for client connections.
   - Once a client connects, the server accepts the connection and establishes a communication channel using a **`Socket`**.
2. **Client-side**:
   - The client creates a **`Socket`** object, specifying the server's IP address and port.
   - The client sends data through the socket, and the server receives it.

This type of communication is typically used for applications such as chat systems, file transfers, etc.

---

### 💻 **Program:**

Here’s a Java program that demonstrates **connection-oriented communication** using a **Socket**. The program is divided into two parts: a **Server** and a **Client**.

#### **Server Program:**

```java
import java.io.*;
import java.net.*;

public class Server {

    public static void main(String[] args) {
        try {
            // Create a server socket listening on port 1234
            ServerSocket serverSocket = new ServerSocket(1234);
            System.out.println("Server is waiting for a connection...");

            // Accept incoming client connection
            Socket clientSocket = serverSocket.accept();
            System.out.println("Client connected!");

            // Set up input and output streams
            BufferedReader in = new BufferedReader(new InputStreamReader(clientSocket.getInputStream()));
            PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);

            // Read and print client message
            String clientMessage;
            while ((clientMessage = in.readLine()) != null) {
                System.out.println("Client: " + clientMessage);
                // Respond to the client
                out.println("Message received: " + clientMessage);
            }

            // Close the streams and the socket
            in.close();
            out.close();
            clientSocket.close();
            serverSocket.close();
        } catch (IOException e) {
            System.err.println("Server error: " + e.getMessage());
        }
    }
}
```

#### **Client Program:**

```java
import java.io.*;
import java.net.*;

public class Client {

    public static void main(String[] args) {
        try {
            // Connect to the server at localhost and port 1234
            Socket socket = new Socket("localhost", 1234);
            System.out.println("Connected to the server!");

            // Set up input and output streams
            BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()));
            PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
            BufferedReader userInput = new BufferedReader(new InputStreamReader(System.in));

            // Send messages to the server
            String message;
            while (true) {
                System.out.print("Enter message to send to server: ");
                message = userInput.readLine();
                if ("exit".equalsIgnoreCase(message)) {
                    break;
                }
                out.println(message);  // Send message to server
                // Receive server response
                System.out.println("Server response: " + in.readLine());
            }

            // Close the streams and the socket
            in.close();
            out.close();
            userInput.close();
            socket.close();
        } catch (IOException e) {
            System.err.println("Client error: " + e.getMessage());
        }
    }
}
```

---

### **Explanation:**

#### **Server Program**:
1. The server listens on **port 1234** using the **`ServerSocket`**.
2. It waits for the client to establish a connection using **`accept()`**.
3. Once connected, the server receives messages from the client using **`BufferedReader`** and sends back responses using **`PrintWriter`**.
4. The server continues to communicate until the client disconnects.

#### **Client Program**:
1. The client connects to the server at **localhost** on **port 1234** using the **`Socket`**.
2. The client sends messages entered by the user to the server using **`PrintWriter`**.
3. The client listens for responses from the server using **`BufferedReader`** and displays them.
4. The loop continues until the user types **"exit"**.

---

### 🖥️ **Output:**

#### **Server Output:**

```
Server is waiting for a connection...
Client connected!
Client: Hello Server!
Server response: Message received: Hello Server!
Client: How are you?
Server response: Message received: How are you?
```

#### **Client Output:**

```
Connected to the server!
Enter message to send to server: Hello Server!
Server response: Message received: Hello Server!
Enter message to send to server: How are you?
Server response: Message received: How are you?
Enter message to send to server: exit
```

---

### ✅ **Conclusion:**

This program demonstrates **connection-oriented communication** using **TCP** sockets in Java. The **server** listens for incoming connections, and the **client** connects to the server and exchanges messages. The communication is reliable and ordered, which is the key feature of TCP. This approach is widely used for applications that require reliable data transmission, such as chat systems, file transfers, and remote procedure calls.
