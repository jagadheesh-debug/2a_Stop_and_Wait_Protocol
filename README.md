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
## SERVER:
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
## CLIENT:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## server
<img width="1091" height="303" alt="Screenshot 2026-11-04 085615" src="https://github.com/user-attachments/assets/49ca9f81-dec7-406f-8208-bef3af79f8f9" />

## client
<img width="751" height="292" alt="Screenshot 2026-11-04 085621" src="https://github.com/user-attachments/assets/ab74f600-ec8c-4998-850b-b556af3624c3" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
