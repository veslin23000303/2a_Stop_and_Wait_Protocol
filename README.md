# 2a_Stop_and_Wait_Protocol
## NAME:VESLIN ANISH A
## REGISTER NO: 212223240175

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
## OUTPUT:
## CLIENT:
![Screenshot 2024-05-15 095732](https://github.com/veslin23000303/2a_Stop_and_Wait_Protocol/assets/151148539/ef37ea6a-bdeb-4cbe-836f-a59ce25f84ee)


## SERVER:
![Screenshot 2024-05-15 095745](https://github.com/veslin23000303/2a_Stop_and_Wait_Protocol/assets/151148539/1820275b-483c-4c4f-b67e-26449915d292)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
