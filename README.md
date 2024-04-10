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
## PROGRAM:

## CLIENT.PY:
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
```
## SERVER.PY:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT:

## CLIENT.PY:

![Screenshot 2024-04-10 163830](https://github.com/dinesh2068/19CS406-EX-NO2-a-/assets/151390189/120f8062-e2e9-466a-a6e8-5665fd9786e6)

## SERVER.PY:

![Screenshot 2024-04-10 163837](https://github.com/dinesh2068/19CS406-EX-NO2-a-/assets/151390189/e3f7b36a-a3c4-4dff-854e-a2c6d71dc414)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
