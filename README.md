# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
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
 print("Frames received:", data)
 ack = "ACK for " + data
 conn.send(ack.encode())
conn.close()
```

client .py
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
 print("Frames received:", data)
 ack = "ACK for " + data
 conn.send(ack.encode())
conn.close()
```
## OUPUT


<img width="903" height="797" alt="Screenshot 2026-05-15 135200" src="https://github.com/user-attachments/assets/1e323ed4-63b8-4074-aba5-076f02e4adcf" />


<img width="912" height="834" alt="Screenshot 2026-05-15 135213" src="https://github.com/user-attachments/assets/0943483e-3ac7-4e70-abe3-58d3328d67cd" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
