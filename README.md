# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links

## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.

## PROGRAM
## SERVER PROGRAM
```
import socket

# Create socket
server = socket.socket()

# Bind IP and port
server.bind(("127.0.0.1", 5555))

# Listen for client
server.listen(1)
print("Server waiting for connection...")

# Accept client
client, addr = server.accept()
print("Connected to:", addr)

# Ask filename
filename = input("Enter file name to send: ")

# Open and send file
with open(filename, "rb") as file:
    data = file.read()
    client.send(data)

print("File sent successfully")

# Close connections
client.close()
server.close()
```
---

## CLIENT PROGRAM
```
import socket

# Create socket
client = socket.socket()

# Connect to server
client.connect(("127.0.0.1", 5555))

# Save file name
save_name = input("Enter name to save file: ")

# Receive data
data = client.recv(1000000)

# Save file
with open(save_name, "wb") as file:
    file.write(data)

print("File received successfully")

# Close connection
client.close()
```

## OUPUT
## SERVER OUTPUT
<img width="1917" height="1021" alt="Screenshot 2026-11-17 151005" src="https://github.com/user-attachments/assets/fc34f784-100f-41ba-8813-d465d4912493" />


## CLIENT OUTPUT
<img width="1917" height="1018" alt="Screenshot 2026-11-17 151051" src="https://github.com/user-attachments/assets/15aef3fc-9c3a-4914-b059-ca068bd48dcc" />


## SAMPLE FILE
<img width="1917" height="1020" alt="Screenshot 2026-11-17 151103" src="https://github.com/user-attachments/assets/fb0a3bcb-7d77-4275-99ba-b639aac41cdc" />


## RECEIVED FILE
<img width="1917" height="1015" alt="Screenshot 2026-11-17 151116" src="https://github.com/user-attachments/assets/d85c6259-d459-417c-bb45-436b709f8ed3" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
