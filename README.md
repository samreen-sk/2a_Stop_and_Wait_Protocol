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
### client
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
### server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### client
![377486691-bd5799ad-4db6-4b4b-b788-30a59eab6cc7](https://github.com/user-attachments/assets/eab9c450-44f9-403b-b327-11403c5b7720)

### server:
![377486768-9ee3057f-bfac-457a-883e-0dedb0529541](https://github.com/user-attachments/assets/7856b507-f11b-4791-8099-cf62f29dd841)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
