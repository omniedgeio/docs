---
title: n2n vs. OmniEdge
route: Doc / Compare / n2n Vs. OmniEdge
index: 5
description: What is the difference between n2n and OmniEdge
thumbnail: /assets/OmniEdge-VPN.svg
---

# n2n vs. OmniEdge

n2n is a light VPN software which makes it easy to create virtual networks bypassing intermediate firewalls. The current OmniEdge is built on top of n2n and we think very high of it. We open source the package with use from n2n, you can found it [here](https://omniedge.io/docs/article/Opensource).

```
An OmniEdge protocol is under developing with OmniEdge's design, which takes the advantages from a lot of p2p protocls including n2n. However, all the features mentioned here will be kept.
```

We designed OmniEdge to make it easier to use p2p connectiong with n2n to secure your network connections. You can choose to use n2n directly, without OmniEdge. 

## Setup

n2n provides two tools to use to make a connection between two nodes. The first is `edge` for nodes, and the other is the `supernode` for the server, and both are necessary. By simply install the n2n package for your linux distributon, you can easily setup up by running the command. To connect two devices, you have to install `edge` on each device, create a network name, generate keys, define IPs for each device. You need to remember all of them for next time use, or you can write into a conf file for each device. The conigraution file includes the information about the device, such as: network name, secrect key, IP address, supernode address, and you need to create the similar file for the other device. Every devices need such a conf file to make a connection, so the number of configuration files grows incredibley in the number of devices, which also make it harder to manage. 

To connect devices using OmniEdge, you just need to log in to OmniEdge on each device, with GUI apps for [windows](/download/windows)，[android](/download/windows),[iOS]() or command cli for [linux](/download/linuxcli), [macOS](/download/macos),[Synology](/download/synology),[Raspberry Pi](/download/rasp), [ARM based Hardware](/download/embedded), [Nvidia Machine Learning Hardware](/download/nvidia). For command cli for all above, you can also run a simple command `curl https://omniedge.io/install/omniedge-install.sh | bash` to install omniedge cli. OmniEdge manages network name, secret key, IP address and all configrautions for you, you can also have a dashboard to manage all your devices, virtual networks and security keys. This is very helpful not only for non-technical users, but technical users to save time. 

## Bonus features

OmniEdge builds a lot of features to improve the connection with n2n. OmniEdge offers the multi virtual network control panel, users can set different IP ranges or same IP ranges for different purpose, or sharing with your virutal netowrk to allow other users to join to have access. For users who need more security, high speed and low lantency, a [custom supernode](/docs#6-customize-supernode) is also avaviable. There are also a security key feature to help login quickly for cli, a device panel to remove or rename to make managment easily. For enterprise users, we can also offer okta, microsoft or other integration authenications. And more features will be developed in the future.

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).