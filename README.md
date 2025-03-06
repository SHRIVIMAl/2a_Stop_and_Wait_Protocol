# 2a_Stop_and_Wait_Protocol
NAME:T.K.SHRIVIMAL

REF NO:21224220101
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
# CLIENT:
~~~
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
~~~
 # SERVER:
 ~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
~~~
## OUTPUT
# CLIENT
![7f7c5cc9-409e-40f7-b846-aa60b08df7de](https://github.com/user-attachments/assets/54504314-fff9-407c-9e80-665f3345a995)

# SERVER
![a3e460e7-a03d-4efa-bcad-ad9114ce74b7](https://github.com/user-attachments/assets/10d5b40c-0dec-4f50-a4b3-7ebe429e3d55)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
