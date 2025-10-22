---
title: "Lập trình mạng với Java Socket"
date: 2024-01-19
draft: false
categories: ["Java"]
tags: ["socket", "networking", "tcp", "udp"]
description: "Hướng dẫn lập trình mạng sử dụng Java Socket"
---

Socket programming cho phép các ứng dụng giao tiếp qua mạng sử dụng TCP/IP.

## TCP Socket Programming

### Server Side
```java
public class SimpleServer {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(8080);
        System.out.println("Server listening on port 8080...");
        
        while (true) {
            Socket clientSocket = serverSocket.accept();
            new ClientHandler(clientSocket).start();
        }
    }
}
```
### Client Side
```java
public class SimpleClient {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket("localhost", 8080);
        PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
        BufferedReader in = new BufferedReader(
            new InputStreamReader(socket.getInputStream()));
        
        out.println("Hello Server!");
        String response = in.readLine();
        System.out.println("Server response: " + response);
        
        socket.close();
    }
}
```
### Multi-threaded Server
```java
class ClientHandler extends Thread {
    private Socket clientSocket;
    
    public ClientHandler(Socket socket) {
        this.clientSocket = socket;
    }
    
    public void run() {
        try {
            BufferedReader in = new BufferedReader(
                new InputStreamReader(clientSocket.getInputStream()));
            PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
            
            String inputLine;
            while ((inputLine = in.readLine()) != null) {
                out.println("Echo: " + inputLine);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
## Ứng dụng thực tế

Chat applications



File transfer



Remote method invocation

