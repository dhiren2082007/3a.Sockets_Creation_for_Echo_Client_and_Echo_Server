# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
### Server:
```
import socket

s = socket.socket()

s.bind(('localhost', 7000))

s.listen(5)

print("Server Waiting...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    if ClientMessage.lower() == "exit":
        break

    c.send(ClientMessage.encode())

c.close()
s.close()
```
### Client:
```
import socket

s = socket.socket()

s.connect(('localhost', 7000))

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    if msg.lower() == "exit":
        break

    data = s.recv(1024).decode()
    print("Server >", data)

s.close()


```

## OUTPUT

### Server:

<img width="889" height="239" alt="image" src="https://github.com/user-attachments/assets/2c0bf3d3-154e-4cdc-8535-9dcf1fb98f2b" />

### Client:

<img width="879" height="197" alt="image" src="https://github.com/user-attachments/assets/133c5e82-f98d-414d-97cb-e620bd381e50" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
