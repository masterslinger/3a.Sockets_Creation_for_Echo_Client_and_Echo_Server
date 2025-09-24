# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
```
Name: Syed Abu Hanifa. L
Reg.no: 212224040346
```
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
CLIENT
```
import socket

HOST = '192.168.31.54'  
PORT = 64856

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
    client_socket.connect((HOST, PORT))

    message = 'Hello, Server!'
    client_socket.sendall(message.encode('utf-8'))

    data = client_socket.recv(1024)
    print(f"Received echo: {data.decode('utf-8')}")
```
SERVER
```
import socket

HOST = '192.168.31.54'  
PORT = 64856        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as server_socket:
    server_socket.bind((HOST, PORT))
    server_socket.listen()

    print(f"Server is listening on {HOST}:{PORT}")
    while True:
        conn, addr = server_socket.accept()
        with conn:
            print(f"Connected by {addr}")
            while True:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)
                print(f"Echoed: {data.decode('utf-8')}")
```
## OUPUT
<img width="1063" height="503" alt="image" src="https://github.com/user-attachments/assets/4fee2463-eb38-4a71-97e2-975fc5fb0cc9" />

<img width="1071" height="763" alt="Screenshot 2025-09-24 100024" src="https://github.com/user-attachments/assets/4ef4dd92-9c67-46d0-a0fe-9ba9f94b7618" />

<img width="1040" height="94" alt="Screenshot 2025-09-24 101609" src="https://github.com/user-attachments/assets/650bf796-4dc2-4e94-bd35-5ff2137e0ff3" />
<img width="1033" height="178" alt="Screenshot 2025-09-24 102025" src="https://github.com/user-attachments/assets/6ef5c815-7815-458c-ae07-f206151da6cc" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
