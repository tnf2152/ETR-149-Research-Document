# What is IRC
Internet Relay Chat, or IRC, is an application layer protocol that shows text communication.
They're basically chat rooms. An IRC Server is the medium that allows communication between multiple IRC Clients.
## IRC Server - Objectives
1. Obtain the correct hardware
2. Find a tutorial for the setup
3. Install and configure IRC Server software
4. Ensure that the server software runs with the configuration
5. Download an IRC Client
6. Connect and test the IRC Server/Client connection
## Setting up the IRC Server - First Try
The first time I tried to setup an IRC server, I decided to use a Windows machine. I thought that a Windows machine would be more easier because i've been using Windows for most of my life. I was only introduced to Linux four years prior to writing this.

When searching for a tutorial with a software recommendation I came across one that said UnrealIRCd was a good option for Windows. The software had a GUI for install, but a text editor for configuring the server. I went through the tutorial on the swiftirc wiki, and followed all of the steps. When I tried to start the program I got an error, when I looked up the error code online I was told to replace the regsvr32.dll file in the Windows folder. When I did, it came up with a new error code. When I looked up this error code, I came across very vague answers on how to fix it. I was on a time constraint so I decided that linux was the better option, but the computer I was using would not let me wipe the hard drive so I had to choose a different machine. 

I think at some point I may have made an error when configuring the server, however with my limited experience I did not know where to look.
## Setting up the IRC Server - Easy as Pi
The computer I decided on next was a Raspberry Pi. I had never used one before and have been wanting to get one myself for a while now. Raspberry Pi runs an OS called Raspbian. Raspbian is a linux OS that is based on Debian architecture. The two distros that I use the most, Ubuntu and Mint both are also Debian based, so I wasn't completely dumbfounded by Raspbian. 

I found a tutorial on [Pimylifeup](https://pimylifeup.com/raspberry-pi-irc-server/ "Pimylifeup"), a site dedicated to Raspberry Pi projects. The best part was all of the installation and configuring would be done with text in the terminal. This project had me install ircd-hybrid instead of the UnrealIRCd program used on the Windows machine using the "sudo apt-get install ircd-hybrid" command. I then had to make a password for my account to access the server later. The password was made in the /etc/bin directory, the encrypted password shown was needed later.

The next part was to configure the server itself. Unlike the UnrealIRCd tutorial, this one had a lot less things for me to configure. There is 1242 lines of text, but only 8 of them had to be modified: The name, description, network details, and the max clients found in the Server info block. Uncommenting the operator block, as well as changing the name, user, and password (encrypted) in that block.  The configuration file was modified in the terminal with a text editor called nano, but any text editor can work. After configuring the software, all I had to do was restart the server.

Once the server was restarted, all I had to do was test it out. The other computers I had access to already had mIRC downloaded. The mIRC client only works on Windows, so if you're using a Mac, I would recommend textual or Limechat. Pidgin and Xchat are popular clients for linux. Adding the server to the mIRC client was straightforward. I had to enter in a description and the IP Address of the server (which can be found by using ifconfig or hostname -I). The only thing left was to click the connect button and make a chatroom(#). Once this was done, I had someone else use a different computer to connect to the same chatroom as me to confirm that it worked.

## Conclusion
Setting up an IRC server is not the hardest thing to do. I made a mistake when I tried to set it up on a Windows computer, but if I found a different tutorial I am sure I would be able to set it up correctly. Setting up the server on linux was a breeze, although I could make it more complicated by adding things like SSH that would make the server more secure if needed. I think that this is a good beginners project that anyone can do.
