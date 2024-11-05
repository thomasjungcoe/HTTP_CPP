What is the HTTP server?
------------------------

    HTTP stands for Hypertext Transfer Protocol.
    It is a standard for sending and receiving data, be it HTML, JSON, or just plain text over the internet.
    HTTP server is simply a computer that serves data over a network via HTTP. It is the basic building block of a web server

        Web Server       <======>           Browser
        -FIles          <- HTTP REQ        PC/Laptop/OS
        -HTTP Server    HTTP REQ->

    so a web server
        * receives this HTTP request and processes it
        * determines the appropriate response after doing certain checks
        * sends this response to the web client

High-Level Design
-----------------
We will be using TCP(Transmission Control Protocol) to implement our HTTP server. TCP is the most common protocol used for HTTP servers, but there are others
    - TCP/IP socket to an IP address on the computer.
    - specific port for listening incoming traffic
    - network connections that come into our server will be stored on a Queue of network threads, processed synchronously

    so basically, 
    
        * listens for incoming network connections and puts them on a Queue
        * accepts a network connection from the Queue one at a time
        * reads the data (Request) sent from the client over the network connection
        * sends data (Response) to the client over the network connection.

OOP design
-----------
The TcpServer class will be a layer of abstration for all of our server code.

http_tcpServer_linux.h & cpp files will hold the code for the actual server implementation via TcpServer class

Server_linux.cpp will have a "main" function through which will run the server using the TcpServer Object.

