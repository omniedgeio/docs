---
title: Remote connect windows without exposing public IP with Omniedge
route: Doc / Cases 
description: Use cases with OmniEdge, Remote connect windows without exposing public IP, and connect them to your private network
thumbnail: /assets/docs/case-aws-windows-1.png
index: 4
---

# Remote connect windows without exposing public IP with Omniedge

AWS or Azure provides a standard RDP(Windows Remote Desktop Protocol) to remotely connect the virtual Windows Server. RDP( Windows Remote Desktop Protocol) is a great tool to remote Windows PC or server over the internet, giving full access to the PCs. When we create a window virtual server, the system will open the **3389** port for the purpose, here in AWS, the setting is done by the **Security groups**. However, RDP has some security problems. 

- RDP exposes public IP on the public internet, everyone who knows the public IP can try to connect or do whatever he wants to pentranate the server. 
- It only allows One remote connection one time.
- RDP is an old technology, developed in 1998 for Windows NT server 4.0.

To have a secure method for the RDP connection, most admins will do: Enable NLA, Eliminate network access to the machine, install System patching, by setting Strict policy and MFA for every login, etc.

It's a very human-intensive job. Fortunately, We have an easy way to improve with Omniedge. With Omniedge, we can make all connections between a local PC to a remote PC with a p2p VPN, keep the connection in a private network, here we will show you how to do it. 

## Step 1. Join the EC2 Team's virtual network.

First RDP connects to your windows EC2 with its public IP, install and Run OMNIEDGE windows Client, join the virtual network of your team, here we have `My Omni Network`, you will have an IP for this EC2, let's say: `100.100.0.153`. After that, your EC2 now joins the team virtual network. 

## Setp 2. Change the `Security groups` for RDP Connect.

Log into your AWS EC2 Console, select your windows EC2, and change the security group setting, in the `Edit Inbouds rules` setting,change the source for RDP from `0.0.0.0/0` to `100.100.0.0/24`. 

```tips
The source CIDR blocks are 0.0.0.0/0 means every IP is allowed to connect to the EC2. While 100.100.0.0/24 limit the connection access from 100.100.0.0 to 100.100.0.254 IP ranges.
```


![](/assets/docs/case-AWS-Security-Groups.png)

## Step 3. RDP Connect by private IP
Connect your virtual network on your own laptop, and open your RDP and input the IP of the AWS EC2 `100.100.0.153`, your AWS EC2 only accepts your private IP ranges now. 

![](/assets/docs/case-aws-windows-1.png)

![](/assets/docs/case-aws-windows-2.png)

## Step 4. VNC Connect by private IP

We recommend [TightVNC](https://www.tightvnc.com), especially you have requirements to copy files in between the source PC and local PC. You can follow [the docs from TightVNC](https://www.tightvnc.com/docs.php) to set up VNC for your windows.

Enjoy!! 

-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).