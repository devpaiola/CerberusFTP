
Purpose of the Script:

The script is an FTP brute-force tool. It attempts to log into an FTP server using credentials from a wordlist, and, upon successful login, provides access to various FTP commands, such as downloading, uploading, renaming files, etc.

Features:

1. Brute-force login attempts: Tries multiple username/password combinations from a wordlist.


2. Post-login FTP commands: If login is successful, it offers several FTP operations such as listing files, navigating directories, downloading/uploading files, and more.



Breakdown of the Code:

Imports: The script uses libraries like os, sys, socket, ftplib, and threading to handle various functions.

socket manages server connections.

ftplib deals with FTP commands.

threading handles multiple login attempts concurrently.


Command Menu (Comandos function): Displays all available commands to interact with the FTP server after login.

Banner function: Displays an ASCII banner when the script starts, clearing the console based on the user's operating system.

Brute-force Section:

The script reads the wordlist file (wordlist_ftp.txt) and splits each line into a username and password.

It attempts to connect to the specified FTP server (rhost and rport) and send the credentials to log in.

If successful, it prompts the user to continue interacting with the server.

If login fails or the server blocks the IP (e.g., too many attempts), it alerts the user and stops.


FTP Commands (After Login): If login is successful, the script offers a command-line interface to the user for interacting with the FTP server. Commands include:

LS - List the directory contents.

CD - Change the directory.

DW - Download a file.

UP - Upload a file.

RN - Rename a file.

EX - Delete a file or directory.

MK - Create a new directory.

PW - Print the current directory path.

RM - Remove a directory.

QT - Quit the session.


Connection Handling:

The script manages exceptions such as ConnectionResetError and TimeoutError and gives the user feedback in case of failure or success.

It also provides an option for passive mode (useful when direct connections are blocked by firewalls).



Code Notes:

1. Threading: Threads are used to handle multiple login attempts concurrently, making brute-forcing faster.


2. Error Handling: The script attempts to catch different types of connection errors and provides informative feedback to the user.


3. Command Input: After logging in, users can interact with the server by typing commands and following the prompts.


