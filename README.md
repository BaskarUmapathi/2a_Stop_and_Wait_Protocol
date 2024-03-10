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
# client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```
# server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
    
```
## OUTPUT
# client
![Screenshot 2024-03-01 145346](https://github.com/BaskarUmapathi/2a_Stop_and_Wait_Protocol/assets/151434098/9515a082-c3fa-4541-8dbc-84ecc974af37)

# server
![Screenshot 2024-03-01 145409](https://github.com/BaskarUmapathi/2a_Stop_and_Wait_Protocol/assets/151434098/d6b1bd03-8f46-4ec6-8b90-a3ffc17a8151)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
