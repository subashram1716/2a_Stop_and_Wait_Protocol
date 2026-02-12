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
server.py
```
import socket 
s=socket.socket() 
s.bind(('localhost',1234))
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
client.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',1234)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
<img width="1919" height="1079" alt="Screenshot 2026-02-12 113220" src="https://github.com/user-attachments/assets/c6087ea9-40ee-4b80-9452-c109f9edfd6b" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
