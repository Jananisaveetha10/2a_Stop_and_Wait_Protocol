# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
7. 
## PROGRAM
```
server:
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

c, addr = s.accept()

while True:
   i = input("Enter a data: ")
   c.send(i.encode())

   ack = c.recv(1024).decode()

   if ack:
       print(ack)
       continue
   else:
       c.close()
       break
client:
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
<img width="977" height="247" alt="Screenshot 2025-09-29 232357" src="https://github.com/user-attachments/assets/8819f86e-17cd-45a4-8990-0eda122255e1" />

<img width="1025" height="254" alt="Screenshot 2025-09-29 232456" src="https://github.com/user-attachments/assets/b68d7bba-eadb-4727-ab24-4b81e4980a74" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
