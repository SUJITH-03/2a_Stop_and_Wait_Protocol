# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
Name : SUJITH A

REGISTER NO : 212224230278

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

### server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)
print("Server listening...")

c, addr = s.accept()
print("Connected:", addr)

while True:
    data = c.recv(1024)
    if not data: break
    msg = data.decode()
    print("Client:", msg)
    c.send(b"ACK")
    if msg.lower() == "exit": break

c.close()
s.close()

```
### client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Enter message for server: ")
    s.send(msg.encode())
    data = s.recv(1024).decode()
    print("Server:", data)

    if msg.lower() == "exit":
        break

s.close()

```
## OUTPUT
<img width="1247" height="316" alt="Screenshot 2025-09-03 104915" src="https://github.com/user-attachments/assets/ef21a4f8-7541-400a-a423-a653e6ee0311" />


<img width="975" height="301" alt="Screenshot 2025-09-03 104926" src="https://github.com/user-attachments/assets/21c4e700-72e9-4ed7-8713-a779eb876c3f" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
