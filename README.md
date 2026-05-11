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
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()

```

```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()
```
## OUTPUT
<img width="1797" height="950" alt="Screenshot 2026-05-11 082832" src="https://github.com/user-attachments/assets/f5e997e5-1823-4225-aa9f-c6fa21192b9f" />

<img width="1656" height="954" alt="Screenshot 2026-05-11 082903" src="https://github.com/user-attachments/assets/9271d8b4-b43c-40dd-8a89-9edc13f83907" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
