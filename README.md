# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:


Server code:
```
# echo-server.py


import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
Client code:

# echo-client.py

```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## OUTPUT

fifile:///home/scoft/Pictures/Screenshots/Screenshot%20from%202023-05-26%2006-09-05.png![image](https://github.com/senoryta/Echoserver/assets/123490411/7dafd32f-02ef-492f-a73e-b7d897fceec7)



file:///home/scoft/Pictures/Screenshots/Screenshot%20from%202023-05-26%2006-09-21.png![image](https://github.com/senoryta/Echoserver/assets/123490411/56ff5acc-bf9a-43a1-83c0-801f59120c1a)


## RESULT
The program is executed successfully
