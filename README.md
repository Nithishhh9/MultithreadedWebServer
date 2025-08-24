# **MultithreadedWebServer**
 
**A simple multithreaded client-server application built in Java.**

It demonstrates TCP socket programming, concurrent client handling using threads, and a minimal request-response protocol.



## *Overview*
This project shows how to:
Build a server that handles multiple clients simultaneously using threads.
Write a client that spawns 100 concurrent connections.
Learn the basics of socket-based network programming in Java.

## *Features*
*Handles multiple concurrent clients via thread-per-connection architecture
Clean, readable Java code—great for beginners and educational use
Easy to extend for additional functionality or protocol changes*

## *Architecture*


+---------------------------+
|                             |
|   Multithreaded Clients     |  ←  100+ client threads run in parallel
|                             |
+---------------------------+

             |
             |     TCP Socket Connections
             v
             
+---------------------------+
|                            |
|    Multithreaded Server    |  ←  New thread created for each client
|                            |
+---------------------------+


### *Server:*

Listens on port 8010
Accepts incoming client connections
Spawns a new thread to handle each client

### *Clients:*
Spawns 100 independent client threads
Each thread establishes a separate TCP session with the server
Sends a greeting and prints the server’s response


## *Installation*
Clone the repository:

bash
git clone https://github.com/nithishhh9/MultithreadedWebServer.git
cd MultithreadedWebServer
Running the Server
Compile and start the server:

bash
javac Server.java
java Server
This will start the server, listening on port 8010.

Running the Clients
In a separate terminal, compile and start the clients:

bash
javac Client.java
java Client
This will spawn 100 client threads, each connecting to the server, sending a message, and printing the received response.

## *How it Works*
Server:
Uses ServerSocket to listen for incoming connections. When a new connection is accepted, it spawns a new thread using the Thread class, passing a lambda that prints a message back to the client and then closes the connection.

Client:
The main method starts 100 threads, each of which:

Connects to the server via TCP

Sends a single greeting line

Receives and prints the server response

Closes the connection


