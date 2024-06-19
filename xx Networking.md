#### Transport Control Protocol

- Built on top of IP (Internet Protocol)
- Assumes ip might lose some Data
    - Stores and retransmits data if it seems to be lost
- Handles “flow control” using a transmit windows.
- provides a nice reliable pipe.

#### TCP connections/Sockets

- In computer networking, an internet socket or network socket is an endpoint of a bidirectional inter-process communication flow across an internet protocol-based computer net work, such as the internet.
![[Connection.png ]]


#### TCP Port Numbers

- A port is an application-specific or process-specific software communications endpoint
- It allows multiple networked applications to coexist on the same server.
- There is a list of well-known TCP port numbers.

#### Sockets in Python

- Python has built-in support for TCP Sockets.
    
```python
import socket
mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect(("data.pr4e.org", 80))
(Host,Port)
```
    

#### Application Protocol

- Since TCP (and Python) gives us a reliable Socket, what do we want to do with the Socket? What problem do we want to solve?
- Application protocols
    - Mail
    - World Wide web

#### HTTP - Hypertext Transfer Protocol

- The Dominant Application Layer Protocol on the internet.
- Invented for the web - to Retrieve HTML, Image, Documents etc.
- Extended to be data in addition to document - RSS, web Services, etc.. Basic Concept - Make a connection - Request a Document - Close the Connection

#### Getting Data from the Server

- Each of the user clicks on an anchor tag with an href= value to switch to a new page, the browser makes a connection to a web server and issues a “GET” request - to GET the content of the page at the specified URL.
- The server return the HTML documents to the browser which formats and displays the documents to the user

#### Networking: write a web browser

```python
# Simple web Browser

import socket

mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect(('data.pr4e.org', 80))
cmd = 'GET <http://data.pr4e.org/romeo.txt> HTTP/1.0\\r\\n\\r\\n'.encode()
mysock.send(cmd)

while True:
    data = mysock.recv(512)
    if len(data) < 1:
        break
    print(data.decode(),end='')
mysock.close()
```

This code demonstrates a simple web browser written in Python. It connects to a specified web server, sends an HTTP request to retrieve a file, and then prints the contents of the file to the console.

Let's break down the code step by step:

1. The code begins by importing the `socket` module, which provides low-level network communication capabilities in Python.
2. Next, a socket object named `mysock` is created using `socket.socket()`. The `AF_INET` argument specifies the address family (in this case, IPv4), and `SOCK_STREAM` indicates that the socket will use a TCP connection.
3. The `connect()` method is called on the `mysock` socket object to establish a connection with the web server. It connects to the server at `'data.pr4e.org'` on port `80`, which is the default port for HTTP.
4. The `cmd` variable is assigned an HTTP GET request for a specific file, in this case, `'<http://data.pr4e.org/romeo.txt'`>. The request is encoded into bytes using the `.encode()` method.
5. The encoded HTTP request is sent to the server using the `send()` method of the socket object.
6. After sending the request, the code enters a `while` loop to receive and print the response from the server. The `recv()` method is used to receive up to 512 bytes of data at a time, which is stored in the `data` variable.
7. The received data is then checked to see if its length is less than 1. If so, it means that there is no more data to receive, and the loop is broken.
8. The received data is printed to the console using `print(data.decode(), end='')`. The `decode()` method converts the bytes data to a string, and `end=''` is used to prevent printing a newline character after each received chunk of data.
9. Finally, the socket connection is closed with `mysock.close()`.

In summary, this code establishes a connection to a web server, sends an HTTP request for a specific file, receives the response in chunks, and prints the contents of the file to the console. It provides a basic illustration of how HTTP requests and responses can be handled using low-level socket programming in Python.

### Networking: Text Processing

### Representing Simple String

- Each character is represented by a number between 0 and 256 stored in 8 bits of memory,
    
- We refer to “8 bits of memory as a “byte” of memory - (i.e. mu disk drive contains 3 Terabytes of memory)
    
- The ord() functions tells us the numeric value of a simple ASCII character.

```python
# Ascii
print(ord("H"))
72
```
    
#### Multi Byte Character

- To represent the wide range of character computers must handle we represent character with more than one Byte.
    - UTF - 16 - Fixed Length - Two Bytes
    - UTF - 32 - Fixed Length - Four Bytes
    - UTF-8 - 1-4 Bytes

#### Networking: Using urllib in python

Since HTTP is so common, we have a library that does all the socket work for us and makes web pages looks like a file.

```python
import urllib.request
fhand = urllib.request.urlopen('<http://data.pr4e.org/romeo.txt>')
for line in fhand:
    print(line.decode().strip())
```