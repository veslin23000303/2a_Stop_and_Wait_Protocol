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
## PROGRAM
```
PROGRAM
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```
SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT
![Screenshot 2024-05-14 184146](https://github.com/23004742/2a_Stop_and_Wait_Protocol/assets/150319318/faf51fab-7e9e-43c9-947f-667c8645fbd6)
SERVER
![Screenshot 2024-05-14 184152](https://github.com/23004742/2a_Stop_and_Wait_Protocol/assets/150319318/934a620f-b5f5-4a01-a060-5e6ebe19e383)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
