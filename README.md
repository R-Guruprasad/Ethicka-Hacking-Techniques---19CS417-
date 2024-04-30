# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:

### server.py
```
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
            data = conn.recv(1024).decode()
            if not data:
                break
            conn.sendall(data.encode())
     

```

### client.py

```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
       s.sendall(input().encode()) 
       data = s.recv(1024).decode()
       print(f"Received {data!r}")

```

## OUTPUT:
### Server Side:
![image](https://github.com/R-Guruprasad/Ethicka-Hacking-Techniques---19CS417-/assets/119390308/e0c8d6f2-57fc-4594-b48f-7d5a2831eeaf)

### Client Side:
![image](https://github.com/R-Guruprasad/Ethicka-Hacking-Techniques---19CS417-/assets/119390308/a9f270f9-8ea7-4774-b8ab-4ddd53bc7ad1)

## RESULT:
The program is executed successfully
