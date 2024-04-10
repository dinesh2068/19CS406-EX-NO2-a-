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

![Screenshot 2024-04-10 161459](https://github.com/dinesh2068/19CS406-EX-NO2-a-/assets/151390189/0c6c2a44-f453-47d9-911a-803dc9183668)

## SERVER.PY:

![Screenshot 2024-04-10 161506](https://github.com/dinesh2068/19CS406-EX-NO2-a-/assets/151390189/67d0f2fc-024f-4d31-8923-5a9a53dc53f5)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
