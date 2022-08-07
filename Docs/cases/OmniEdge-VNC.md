---
title: Display and control macOS, Linux and Windows with Omniedge 
route: Doc / Cases / VNC
description: Use cases with OmniEdge, Remote connect windows VNC
thumbnail: /assets/docs/case-omniedge-vnc.png
index: 4
---

# Display and control macOS, Linux and Windows with Omniedge 

In computing, Virtual Network Computing (VNC) is a graphical desktop-sharing system that uses the Remote Frame Buffer protocol (RFB) to remotely control another computer. It transmits the keyboard and mouse input from one computer to another, relaying the graphical-screen updates, over a network. VNC is platform-independent – there are clients and servers for many GUI-based operating systems and for Java. 

Multiple clients may connect to a VNC server at the same time. Popular uses for this technology include remote technical support and accessing files on one's work computer from one's home computer, or vice versa.

With [OmniEdge](https://omniedge.io/download), VNC can have a wonderful feature, replace expensive tools by OmniEdge's peer-to-peer network, remote control computres from anywhere, anytime.

VNC's features include:

- Remote Control
- Cross-platformm, PC to PC, Mobile to PC across Windows, Mac, Linux, iOS, and Android.
- File transfer
- And More

![](/assets/docs/case-omniedge-vnc.png)

## Requirements

- Install OmniEdge for your [macOS](https://omniedge.io/download/macOS), [linux](https://omniedge.io/download/linuxcli), or [windows](https://omniedge.io/download/windows), and on your [android](https://omniedge.io/download/android) devices. Read the [OmniEdge Installation Instruction](https://omniedge.io/docs/article/Install) to install OmniEdge. 

- Install VNC Servers and Clients, you can use [TightVNC](https://www.tightvnc.com) or [REALVNC](https://www.realvnc.com/en/)for windows. 


## Install TightVNC for Windows

Download [TightVNC](https://www.tightvnc.com/download.php), and install it. TightVNC runs on any version of Windows. 

You can refer the Doc: [TightVNC for Windows: Installation and Getting Started (PDF)](https://www.tightvnc.com/doc/win/TightVNC_for_Windows-Installation_and_Getting_Started.pdf) to install and get TightVNC running. 

### Install TightVNC。

For Windows 64bit：[tightvnc-2.8.27-gpl-setup-64bit.msi](https://www.tightvnc.com/download/2.8.27/tightvnc-2.8.27-gpl-setup-64bit.msi)

For Windows 32bit: [tightvnc-2.8.27-gpl-setup-32bit.msi](https://www.tightvnc.com/download/2.8.27/tightvnc-2.8.27-gpl-setup-32bit.msi)

Double click and follow the instructions to install. 


### Run and Setup TightVNC Server。

After run TightVNC Server, you can see a tray icon,：

![](/assets/docs/case-VNC-omniedge-1.png)

Setup the password for remote control by right clicking the tray icon of TightVNC Server：

![](/assets/docs/case-VNC-omniedge-2.png)

Click Configuration Menu, Set the password and remember

![](/assets/docs/case-VNC-omniedge-3.png)

## Install TightVNC for Ubuntu 20.04 Server

```bash
sudo apt update
# install the Desktop Environment xfce4 if not installed 
sudo apt install xfce4 xfce4-goodies -y
sudo apt install tightvncserver -y
```

Run the `vncserver` command to set a VNC access password, create the initial configuration files, and start a VNC server instance:

```bash
vncserver
```

You need setup `password` after for vnc login.
The app launches a default vnc server instance on port `TCP 5901` which is a display port, and is referred to by VNC as :1. VNC can launch multiple instances on other display ports, with :2 referring to port 5902, :3 referring to 5903, and so on.

You can stop `vncserver` by running `vncserver -kill :1`.

```bash
vncserver -kill :1
```

### Run VNC Server as a service

```bash
sudo vim /etc/systemd/system/vncserver@.service
```

Paste the below text:

```bash
#/etc/systemd/system/vncserver@.service
[Unit]
Description=Start TightVNC server at startup
After=syslog.target network.target

[Service]
Type=forking
User=ubuntu
Group=ubuntu
WorkingDirectory=/home/ubuntu

PIDFile=/home/ubuntu/.vnc/%H:%i.pid
ExecStartPre=-/usr/bin/vncserver -kill :%i > /dev/null 2>&1
ExecStart=/usr/bin/vncserver -depth 24 -geometry 1280x800 -localhost :%i
ExecStop=/usr/bin/vncserver -kill :%i

[Install]
WantedBy=multi-user.target
```

Save the file, and make the service run by :

```bash
sudo systemctl daemon-reload
sudo systemctl enable vncserver@1.service
vncserver -kill :1
sudo systemctl start vncserver@1
sudo systemctl status vncserver@1
```

The 1 following the @ sign signifies which display number the service should appear over, in this case the default :1. you can run :2 with `sudo systemctl enable vncserver@2.service`.

**The VNC port of ubuntu is `5901` for :1 or `5902` for :2**

## Installing OmniEdge Windows

You need install omniedge on every machine you want to connect, here we take windows for example. If you remote computer is using a different OS, please refer [OmniEdge Download](https://omniedge.io/download) to download related version of OmniEdge. 

OmniEdge Windows is compatible with Windows 7,10(arm) & Windows Server 2016,2019. `Last update: Version 0.2.2, January 16,2022.`

[Download OmniEdge Windows for 7 or later](https://github.com/omniedgeio/app-release/releases/download/v0.2.2/omniedge-setup-0.2.2.exe)

+ Download and run the Windows installer

+ Click on "Log in…" from the Omniedge icon now in your system tray

+ Sign in with your email address

+ Click "Connect" in the menu bar from the tray icon. After a pop-up disappears, a secure VPN connection is initialized.


## Remote Control a friend's Computer

You can invite your friend to your virtual network, and remote support and control your friend's computer through VNC. You friend's computer needs to install VNC and running OmniEdge as well. 

![](/assets/docs/case-Omniedge-Invite.png)

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).