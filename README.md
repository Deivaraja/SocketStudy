# Ex.No:1a  			Study of Socket Programming

## Aim: 
To perform a study on Socket Programming
## Introduction:

 Socket programming is a crucial aspect of network communication, allowing for data exchange between computers over a network. It forms the backbone of various networked applications, enabling communication between clients and servers. This study explores the fundamental concepts of socket programming, its use cases, and provides a practical example to demonstrate its implementation.
## Understanding Socket Programming:
 Socket programming involves the use of sockets, which serve as endpoints for communication. A socket is identified by an IP address and a port number, and it facilitates data transfer between a client and a server. The two main types of sockets are Stream Sockets, which provide a reliable, connection-oriented communication, and Datagram Sockets, which are connectionless and suitable for scenarios where reliability is less critical.
## Key Concepts in Socket Programming:
1.Sockets
•	A socket is a software representation of a communication endpoint in a network.
•	It is identified by an IP address and a port number.
•	Sockets can be classified into two main types: Stream Sockets and Datagram Sockets.
•	Stream Sockets provide a reliable, connection-oriented communication, while Datagram Sockets are connectionless and operate in a best-effort mode.

2. Client-Server Model

•	Socket programming typically follows the client-server model.
•	The server listens for incoming connections from clients, while clients initiate connections to the server.
•	Servers are passive, waiting for connection requests, and clients are active, initiating communication.

3, TCP/IP Protocol:

•	Transmission Control Protocol (TCP) and Internet Protocol (IP) are the foundational protocols for socket programming.
•	TCP provides reliable, connection-oriented communication, ensuring data integrity and order.
•	IP facilitates the routing of data between devices in a network.

4.Basic Socket Functions:

•	Socket programming involves a set of functions provided by the operating system or programming language to create, bind, listen, accept, connect, send, and receive data through sockets.
•	Examples of functions include socket(), bind(), listen(), accept(), connect(), send(), and recv().

## Server-Side Operations:

•	Servers create a socket using socket() and bind it to a specific IP address and port using bind().
•	They then listen for incoming connections with listen() and accept connections with accept().
•	Once a connection is establi
•	shed, servers can send and receive data using send() and recv().

## Client –Server Operations

Clients create a socket using socket() and connect to a server using connect().
After establishing a connection, clients can send and receive data using send() and recv().

## Use Cases of Socket Programming:
Socket programming finds applications in various domains, including web development, file transfer protocols, online gaming, and real-time communication. It is the foundation for protocols like HTTP, FTP, and SMTP, which power the internet. Socket programming enables the development of both server and client applications, facilitating the exchange of information between devices in a networked environment.
## Example Use Cases:

1.Time Synchronization Service:
In distributed systems, synchronized time is crucial. This program can serve as a foundation for a basic time synchronization service, where a central server provides the current date and time to connected clients.
2.Event Logging Systems:
Centralized servers can provide a timestamp to client machines, ensuring that all logged events across systems have a consistent and accurate time reference.
3.IoT Device Coordination:
In IoT networks, devices may request the current time from a server after reboot or startup, using this information to schedule operations or log sensor data correctly.
4.Automated Job Scheduling:
Remote clients may request the current time to align with server-scheduled jobs or tasks, ensuring accurate execution timing in systems like grid computing or backups.
5.Educational Purpose:
The program is ideal for teaching the basics of socket programming, illustrating key concepts such as socket creation, binding, listening, accepting connections, sending and receiving data, and client-server interaction.

## Program :



## server.py
~~~
import socket
s = socket.socket()
s.connect(('localhost', 8000))
data = s.recv(1024).decode()
print("Received from server:", data)
s.send("Time received successfully.".encode())
s.close()
~~~

 ## Client.py
~~~
import socket
from datetime import datetime
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Waiting for a client to connect...")
c, addr = s.accept()
print("Client Address:", addr)
now = datetime.now()current_time = now.strftime("%d/%m/%Y %H:%M:%S")
c.send(current_time.encode())
ack = c.recv(1024).decode()
if ack:
    print("Acknowledgment from client:", ack)

c.close()

~~~
## Output :
<img width="1496" height="1072" alt="{B17647F9-DC08-43E3-8520-56DF760DEEA1}" src="https://github.com/user-attachments/assets/af8e55ee-3569-4d91-a38f-bd1469c37d47" />
<img width="1484" height="1020" alt="{F1ED5D39-0A04-42C3-8B45-E5283E9F238B}" src="https://github.com/user-attachments/assets/9e9aa873-5ce0-495c-aef3-25110bf872f9" />




## Result:
Thus the study of Socket Programming Completed Successfully
