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
Client:
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
Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT



![330666305-5f4dbcef-1a1f-48de-9e40-cff3b7c992bd](https://github.com/Subhikshaa13/2a_Stop_and_Wait_Protocol/assets/118787344/b9941a4e-0cd8-4f4b-9de9-8d38360f3395)

![330666268-d2097e09-d2e9-4dde-818b-e6141f136f49](https://github.com/Subhikshaa13/2a_Stop_and_Wait_Protocol/assets/118787344/6803f21a-a24c-4ca8-90bb-17e5f2d09f52)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
