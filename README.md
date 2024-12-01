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

Video File Transfer via TCP (Client-Server Model)
This assignemnt implements a client-server model using GNU C and TCP sockets for transferring video files. The sender (client) uses a GTK GUI for file selection and monitoring, while the receiver (server) saves the file.

Architecture

Sender (Client):
Reads the video file in binary mode.
Splits the file into fixed-size chunks (e.g., 1KB/4KB).
Sends chunks to the server over a TCP connection.
Signals end-of-transmission with a termination message (e.g., "EOF").

Receiver (Server):
Accepts incoming client connections.
Saves received chunks to a new video file in binary mode.
Monitors for the "EOF" marker to finalize the transfer.

Steps to Implement

Sender (Client):
Create a TCP socket (socket()).
Connect to the server (connect()).
Open the video file (fopen() in binary mode).
Read and send chunks (fread() + send()).
Signal end-of-transmission ("EOF") and close the socket.

Receiver (Server):
Create a listening socket (socket() + bind() + listen()).
Accept client connections (accept()).
Open a new video file for writing (fopen() in binary mode).
Receive and write chunks (recv() + fwrite()).
Detect "EOF", close the file and socket.

Technologies Used:
GNU C for socket programming.
GTK for GUI (on the client side).
This structure ensures efficient, reliable video file transfer over a TCP connection.



