# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
## SERVER:
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)
print("Server is waiting for connection...")
c, addr = s.accept()
print("Connected to:", addr)
while True:
    client_msg = c.recv(1024).decode()
    if not client_msg:
        break
    print("Client >", client_msg)
    msg = input("Server > ")
    c.send(msg.encode())
c.close()
s.close()
```
## CLIENT:
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    s.send(msg.encode())
    server_msg = s.recv(1024).decode()
    if not server_msg:
        break
    print("Server >", server_msg)
s.close()
```
## OUTPUT
<img width="890" height="325" alt="image" src="https://github.com/user-attachments/assets/5e0ec593-8e4c-4e5d-90ad-2f3e874cb845" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
