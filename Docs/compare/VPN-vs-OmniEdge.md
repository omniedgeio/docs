---
title: VPN vs. OmniEdge
route: Doc / Compare / VPN vs. OmniEdge
index: 5
description: What is the difference among VPN, dVPN, Tor, blockchain VPN and OmniEdge
thumbnail: /assets/OmniEdge-VPN.svg
---

# VPN vs. OmniEdge

## What is the difference between OmniEdge and VPNs?

A **virtual private network (VPN)** extends a private network across a public network and enables users to send and receive data across shared or public networks as if their computing devices were directly connected to the private network. There is always a VPN server that provides such services. The Users connect to the server and are replayed by the server. 

**OmniEdge** doesn't need any central Sever, which creates a peer-to-peer tunnel between two nodes, builds a virtual network for all the devices which connect to each other. 

## Benefits of OmniEdge vs. VPNs,dVPNs, Blockchain VPNs

With OmniEdge, you: 

- Don't need any VPN server anymore.
- Don't need any VPN gateway for your company's different branches. 
- OmniEdge provide a peer-to-peer connection between devices without server relay, while VPN always reley on your connections. 

![OmniEdge](/assets/OmniEdgeComparison.gif)


## Basic Information

|Software|Version|Linux/Windows/MacOS/BSD|iOS/Android|
|---|---|---|---|
|OpenVPN|2.4.11|Yes/Yes/Yes/Yes|Yes/Yes|
|Wireguard|1.0|Yes/Yes/Yes/Yes|Yes/Yes|
|OmniEdge|0.1.0|Yes/Yes/Yes/Yes|Yes/Yes|


## Networking features
|Software|TUN/TAP|Auto meshing|NAT Traversal|Protocol|
|--|--|--|--|--|--|
|OpenVPN|Yes/Yes|No|(Yes)|UDP/TCP|
|Wireguard|Yes/No|No|No|UDP|
|OmniEdge|No/Yes|Yes|Yes|UDP|

## Security features
|Software|Cipers|
|--|--|
|OpenVPN|AES256(OpenSSL)|
|Wireguard|ChaCha20|
|OmniEdge|Twofish,AES128,ChaCha20|

## Performance

|Through put test|Bandwidth|
|--|--|
|Native Network|4970 Mbit/s|
|OpenVPN||
|Wireguard|3810 Mbit/s|
|OmniEdge|3470 Mbit/s|


-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).