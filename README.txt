CNT 5106 Computer Networks:
Project I: Implementation of FTP Client and Server


Description: 
In this project, I have implemented a simple version of FTP client/server software. It
consists of two programs: FtpFileServer and FtpFileClient. First, the FtpFileServer is started on a
computer. It listens on a certain TCP port. Then, the FtpFileClient is executed on the same computer; the server’s address and port number are supplied in the command
line, for example, “FtpFileClient sand.cise.ufl.edu 5106”. The client will prompt for username
and password. After logon, the user can issue three commands at the client side: 
(a)“dir” isto retrieve the list of file names available at the server 
(b) “get <filename>” is to retrieve afile from the server, and 
(c)“upload < filename>” is to upload a file to the server.

Instructions for running the code:

(1) Go to Project1 > src
(2) Under src, go to Source Folder > FtpFileServer.java
(3)Under src, go to Client Folder > FtpFileClient.java
(4) First, Compile and Run "FtpFileServer.java" on command prompt/terminal
(5) After that, Compile and Run "FtpFileClient.java" on two separate command prompts for Client Application
(6) Then, execute command: "java –cp [File Path] FtpFileClient localhost 25441" under the Client Application, since this command includes the correct IP and Port number
(7) After that type the correct login and password, then the user will be successfully logged in
(8) Then, Execute the multiple commands/ test cases.  

Detailed Steps:

To run on Terminal or Command Prompt, the steps are as follows:
(1) First of all, run the application of the Server as,  java FtpFileServer
Heyy!! Server started.
Waiting for a Client.......

(2) After that, run the Client Application on other Command prompt as, java –cp [File Path] FtpFileClient localhost 25441 by entering the prior command. 
It will show:
Please enter your username
Anushri
Please enter your password

But, if we will enter the incorrect IP or Port number, then it will refuse the connection and will display as, "Cannot connect to the server, try again later."

Now, after entering the correct username and password, at the client side, it will show as,
"User Anushri Successfully logged in"

If you will enter the incorrect password or username, then after 2 attempts, the system will automatically shut down, since, I have set the maximum attempts=2, so it will show the message as "Incorrect details! Please try again
You have exceeded max limit"), then we have to start it again.

And at the Server application, it will display as, 
"Accepted connection : Socket[addr=/127.0.0.1,port=51024,localport=25441]"

(3) After successfully logged in: We will get the following:

Please choose from given Options:

upload <fileName> : To Upload files
dir                          : To get List of Files.
get <fileName>       : To Download file.
logout                     : To log out and Exit.

Now try all these commands from both the Clients.
(a) Let's say we have typed "dir command": Then at client application, we will get all the files i.e. available with Server and at the same time, at the Server application, we will get the following:

"List command received at Server"
"Accepted connection : Socket[addr=/127.0.0.1,port=51033,localport=25441]"

(b) If we have typed "upload <fileName>" command: then it will upload the corresponding file name to the server (eg: upload testclient1.txt) and will display the following message.

"File testclient1.txt sent to Server"

And at the same time, the Server will receive the request and will display the following:

"Upload command received at Server
Accepted connection : Socket[addr=/127.0.0.1,port=51038,localport=25441]
File testclient1.txt received from client"

After this we will again receive the list of the commands at the client end.

(c) Then, next if we have typed the "get <fileName>" command: then this command will download a file from the server. Let's say we can try this command from the Client 2, that will open on another command prompt:
Follow the same steps for the Client 2 as followed for Client 1 and after that we will get the list of commands, then type "get <fileName>" command. Here, we will download the same file that we have uploaded from Client 1 to server.

Eg: get testclient1.txt and it will display the following message at the client application:

"File testclient1.txt received from Server."

And at the same time, the Server will receive the request and will display the following:

"Download command received at Server
File testclient1.txt sent to client.
Accepted connection : Socket[addr=/127.0.0.1,port=51052,localport=25441]"

After this we will again receive the list of the commands at the client end.

(d) So, we can perform multiple cases as we want like, Command "ftpclient <IP port>" with wrong IP or port number

(e) Try logging in with the wrong username or password

(f) Try uploading a file that doesn’t exist

(g) Command “dir” from client 2

(h) Try “get” wrong file name

