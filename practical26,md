### 💡 **Aim:**
Write a program to demonstrate **sending and receiving data** through a **Datagram** in Java.

---

### 📘 **Theory:**

In Java, **Datagram** communication is connectionless and uses the **UDP (User Datagram Protocol)** for sending and receiving packets. It is part of the **java.net** package and is often used for simple, fast communication where reliability and ordering of packets are not critical (e.g., real-time applications like gaming, video streaming, etc.).

- **DatagramSocket**: A class used to send and receive **datagrams**.
- **DatagramPacket**: A class that encapsulates the data being sent or received. It contains the message (data), the address, and the port information.

Key steps:
1. A **DatagramSocket** is created on both the sender and receiver sides.
2. A **DatagramPacket** is created to store the data and the destination details (address, port).
3. The sender uses the **send()** method of the **DatagramSocket** to send the packet.
4. The receiver uses the **receive()** method to read the incoming packet.

UDP is faster but less reliable than TCP, as it does not guarantee delivery or ordering of packets.

---

### 💻 **Program:**

Here’s a Java program that demonstrates sending and receiving data through **Datagram**. The program is divided into two parts: **Sender** and **Receiver**.

#### **Receiver Program**:

```java
import java.net.*;  
import java.io.*;  

public class DatagramReceiver {

    public static void main(String[] args) {
        DatagramSocket socket = null;
        try {
            // Create a DatagramSocket to listen on port 9876
            socket = new DatagramSocket(9876);
            byte[] receiveData = new byte[1024];

            System.out.println("Receiver is ready to receive messages...");

            while (true) {
                // Create a DatagramPacket to receive data
                DatagramPacket receivePacket = new DatagramPacket(receiveData, receiveData.length);

                // Receive the packet
                socket.receive(receivePacket);

                // Convert received bytes into a string and print it
                String message = new String(receivePacket.getData(), 0, receivePacket.getLength());
                System.out.println("Received message: " + message);

                // Stop the receiver when "exit" message is received
                if (message.equalsIgnoreCase("exit")) {
                    break;
                }
            }
        } catch (Exception e) {
            System.err.println("Error in receiver: " + e.getMessage());
        } finally {
            if (socket != null && !socket.isClosed()) {
                socket.close();
            }
        }
    }
}
```

#### **Sender Program**:

```java
import java.net.*;  
import java.io.*;  

public class DatagramSender {

    public static void main(String[] args) {
        DatagramSocket socket = null;
        try {
            // Create a DatagramSocket
            socket = new DatagramSocket();

            InetAddress receiverAddress = InetAddress.getByName("localhost");  // Receiver address
            int receiverPort = 9876;  // Port on which the receiver is listening

            // Send messages
            BufferedReader userInput = new BufferedReader(new InputStreamReader(System.in));
            String message;
            while (true) {
                System.out.print("Enter message to send: ");
                message = userInput.readLine();

                // Convert message to byte array
                byte[] sendData = message.getBytes();

                // Create a DatagramPacket to send the data
                DatagramPacket sendPacket = new DatagramPacket(sendData, sendData.length, receiverAddress, receiverPort);

                // Send the packet
                socket.send(sendPacket);

                // Stop if user types "exit"
                if (message.equalsIgnoreCase("exit")) {
                    break;
                }
            }
        } catch (Exception e) {
            System.err.println("Error in sender: " + e.getMessage());
        } finally {
            if (socket != null && !socket.isClosed()) {
                socket.close();
            }
        }
    }
}
```

---

### **Explanation:**

#### **Receiver Program**:
1. The receiver creates a **DatagramSocket** on port `9876` to listen for incoming datagrams.
2. It uses a **DatagramPacket** to receive data. The `receive()` method waits for incoming packets.
3. Once a packet is received, it converts the byte array into a string and prints the message.
4. The receiver stops when it receives an **"exit"** message.

#### **Sender Program**:
1. The sender creates a **DatagramSocket** and specifies the **receiver's address** (localhost) and port (9876).
2. It reads messages from the user, converts them into byte arrays, and creates a **DatagramPacket** to send the data.
3. The **send()** method is used to send the packet to the receiver.
4. The sender stops when the user types **"exit"**.

---

### 🖥️ **Output:**

#### **Receiver Output**:

```
Receiver is ready to receive messages...
Received message: Hello, Receiver!
Received message: How are you?
Received message: exit
```

#### **Sender Output**:

```
Enter message to send: Hello, Receiver!
Enter message to send: How are you?
Enter message to send: exit
```

---

### ✅ **Conclusion:**

This program demonstrates how to send and receive data using **Datagram** in Java through **UDP**. The **DatagramSocket** class is used to send and receive data, while **DatagramPacket** encapsulates the data being transferred. This connectionless communication method is faster but does not guarantee delivery or ordering, making it suitable for applications where speed is critical but reliability is not a top priority.
