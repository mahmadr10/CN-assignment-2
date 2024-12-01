# CN-assignment-2

Contribution:

1.	Muhammad Ahmad:
•	Logic building
•	Execution of file transfer
•	Verification
•	GitHub work

2.	Tahir Mehmood:
•	Optimization
•	Verification
•	Execution of file transfer
•	Documentation


Online video Link for a demo, including an audio description of the both codes and execution of the file transfer:

https://drive.google.com/file/d/1W_wnuB9EXqMyOHVNeis8IZC1i2oWAbV8/view?usp=sharing





Approach:
This assignment implements a client-server model over TCP using sockets in GNU C. The objective is to transfer a video file from a sender (client) to a receiver (server). The sender uses GTK for a GUI to select the file and monitor progress, while the receiver saves the video in a designated file. Below is the revised approach.



                                    Architecture and Workflow

1. Sender (Client) Side
•	Open and read the video file in binary mode.
•	Split the video file into fixed-size segments (e.g., 1KB or 4KB chunks).
•	Use a TCP socket to connect to the receiver (server).
•	Transmit each segment one by one until the complete file is sent.
•	Indicate the end of the transmission with a special marker or message (e.g., EOF).
•	Close the socket once the video file is fully transmitted.
2. Receiver (Server) Side
•	Set up a TCP listening socket to accept incoming connections.
•	Open a new video file to write the incoming data in binary mode.
•	Receive the video in segments and write them to the newly created file.
•	Monitor for the EOF indicator to detect the end of the file transmission.
•	Close the file and socket after the file transfer is complete.

Steps to Implement

Sender Side (Client)
1.	Create a TCP socket using the socket() system call.
2.	Connect to the server using connect().
3.	Open the video file in binary mode using fopen().
4.	Read the file in chunks using fread() inside a loop.
5.	Transmit each chunk using the send() system call.
6.	Send a termination message (e.g., EOF) to signal the end of the file transfer.
7.	Close the file and socket after transmission is complete.
Receiver Side (Server)
1.	Create a listening socket using the socket() system call.
2.	Bind the socket to a port using bind().
3.	Use listen() to wait for incoming client connections.
4.	Accept incoming connections using accept().
5.	Open a new video file in binary mode using fopen() to store the received data.
6.	Use recv() in a loop to receive data and write it to the file using fwrite().
7.	Detect the EOF message to terminate the loop.
8.	Close the file and socket after the transfer is complete.
                                                                   

