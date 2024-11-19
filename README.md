# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
## PROGRAM - RARP
```
client:

import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())

server:


import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
ip=input("Enter logical Address : ") 
s.send(ip.encode())
print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![383514611-7d9abdd1-1e2d-4d6c-a4b1-71e378367473](https://github.com/user-attachments/assets/7b00c5dd-b4da-4627-82df-46ebebcc904c)

![383514826-f1f4830e-fb31-4580-ab6a-58ff794804d8](https://github.com/user-attachments/assets/0258f8f5-7116-4ad8-9126-8f86c6ee0254)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
