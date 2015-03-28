How to install smartVISU on a Debian based Webserver

# Introduction #

It is quite easy to install smartVISU on a Webserver. This tutorial discribes, how to setup a server with eibd, LinKNX and smartVisu on Debian.

**required hadware:**
  * a server, with internet connection, of you choise...

**required software:**

To run smartVISU on your system you need the following prerequisites:
  * debian based operating system
  * EIBD
  * LinKNX
  * webserver with PHP 5.2.4 (f.e. Apache2)
  * latest version of smartVISU

# Installation #

I like to use a slim server for my enviroment, so i use [Debian-Netinst-Image](http://www.debian.org/CD/netinst/). Download the image for your system architecture. Burn disk and run setup. You can use any Debian based Linux operating system, like Ubuntu and other derivates.

For my system, i just use the base system of debian. This is without a GUI (X-Windows). The webserver i like to use is Apache 2 and thats all for my basic setup. Setup a fixed IP address for this server. I manage my server via a SSH connetion, see Setup SSH fo further information.

## Setup SSH ##

If you like to use SSH to mange your server, follow this section or skip to next section.

The first thing i setup directly on my server, before removing screen, mouse and keyboard is [SSH](http://en.wikipedia.org/wiki/Secure_Shell). So my server has no screen, mouse and keyboard. I use a SSH form an other linux based system to configure my system. You can use [Putty](http://putty.softonic.de/download) on windows based system to access your server via SSH.

  1. Before removing mouse, screen, and keyboard from server
    * We need to setup the shh server
    * Login as root to your server, with passwords from setup
    * Run the following commands:
```
apt-get update
apt-get install ssh
```
    * This will install and setup the SSH server
    * Now we cann access the server via SSH from an other computer in the same network
    * Connect to a server from an other linux system run:
```
ssh IP_OF_YOUR_SERVER
```
    * Connection from Windows:
      * download and run [Putty](http://putty.softonic.de/download) enter IP of your server and connect

## Setup eibd ##

Eibd is not part of the debian sources, so we have to add a repository to the source list.

I like to use [nano](http://www.debianadmin.com/nano-editor-tutorials.html) as text editor. This tutorial uses nano to edid files. You can use what ever you prefer.

  * needed nano commands: save file (Ctrl + o), close file = Ctrl + x

  * lets go:
  * open the source file:
```
nano /etc/apt/sources.list
```
  * now add at the end the following lines:
```
deb http://www.auto.tuwien.ac.at/~mkoegler/debian eib main
deb-src http://www.auto.tuwien.ac.at/~mkoegler/debian eib main
```
  * save file (press Ctrl + o, then press enter)
  * close file (press Ctrl + x)
  * the repository is signed with a key so we need to add it to our system:
```
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3CB5CB58
```
  * Install eibd:
```
apt-get update
apt-get install bcusdk
```
  * so now eibd is on your server

### test eibd ###

### autorun eibd ###

### use USB interface ###