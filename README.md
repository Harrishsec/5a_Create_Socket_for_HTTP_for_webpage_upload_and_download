# 5a_Create_Socket_for_HTTP_for_webpage_upload_and_download
## AIM :
To write a PYTHON program for socket for HTTP for web page upload and download
## Algorithm

1.Start the program.
<BR>
2.Get the frame size from the user
<BR>
3.To create the frame based on the user request.
<BR>
4.To send frames to server from the client side.
<BR>
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
<BR>
6.Stop the program
<BR>
## Program 

## CLIENT.PY
~~~py
# Simple program to download a webpage using HTTP socket

import socket

# Create socket
s = socket.socket()

# Connect to website (HTTP - port 80)
s.connect(("example.com", 80))

# Send GET request
s.send(b"GET / HTTP/1.1\r\nHost: example.com\r\n\r\n")

# Receive data
data = s.recv(4096)

# Print webpage content
print(data.decode())

# Close connection
s.close()

~~~

## SERVER.PY
~~~py
# Simple program to upload data using HTTP POST request

import socket

# Create socket
s = socket.socket()

# Connect to test server
s.connect(("httpbin.org", 80))

# Data to send
data = "name=Harrish&message=Hello"

# Create POST request
request = "POST /post HTTP/1.1\r\nHost: httpbin.org\r\nContent-Type: application/x-www-form-urlencoded\r\nContent-Length: {}\r\n\r\n{}".format(len(data), data)

# Send request
s.send(request.encode())

# Receive response
response = s.recv(4096)

# Print response
print(response.decode())

# Close connection
s.close()

~~~
## OUTPUT

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/232abab5-b374-48da-9c2e-2077caf60d9d" />

## Result
Thus the socket for HTTP for web page upload and download created and Executed
