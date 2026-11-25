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

s = socket.socket()
s.connect(('localhost', 8000))

data = ["Frame 1", "Frame 2", "Frame 3", "Frame 4"]

for frame in data:
    print("Sending:", frame)
    s.send(frame.encode())

    ack = s.recv(1024).decode()
    print("Acknowledgement received:", ack)

s.close()
```
## CLIENT:
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Receiver is waiting...")
c, addr = s.accept()

while True:
    data = c.recv(1024).decode()

    if not data:
        break

    print("Received:", data)

    ack = "ACK"
    c.send(ack.encode())
    print("Acknowledgement sent:", ack)

c.close()
s.close()
```
## OUTPUT
## server
<img width="486" height="278" alt="image" src="https://github.com/user-attachments/assets/1169d91d-7931-4c90-9d2c-378f08d76135" />

## client
<img width="470" height="288" alt="image" src="https://github.com/user-attachments/assets/fa6d9c33-4e16-4c71-8ab1-d82beff12284" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
