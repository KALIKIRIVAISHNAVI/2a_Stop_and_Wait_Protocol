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
## client
```
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
## server
```
   import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## client
![image](https://github.com/KALIKIRIVAISHNAVI/2a_Stop_and_Wait_Protocol/assets/152273289/518792e5-77f2-43bb-b7f2-1a3e1e3935e0)
## server
![image](https://github.com/KALIKIRIVAISHNAVI/2a_Stop_and_Wait_Protocol/assets/152273289/edfb7cca-95e4-4cb1-9525-7ce987891ab5)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
