---
title: Customize Supernode Installation
description: OmniEdge offers customize supernode, You can setup your own Supernode server to increase security and speed for your Private Network.
route: Docs / Install / Customize Supernode
index: 3
thumbnail: /assets/docs/OmniEdge-CustomizeAuthServer.png
---

# Customize Supernode

OmniEdge runs default supernode servers to help connect your nodes. However, OmniEdge also offers customize supernode, you can run your own. 

# What are the supernode servers ? 

OmniEdge runs Supernode servers distributed around the world to 
coordinates the communication between nodes within the virtual network, help your omniedge nodes connect peer-to-peer, and as a fallback to relay traffic between nodes in case NAT traversal fails and a direct connection can not be established. 

OmniEdge runs supernode servers in Hong Kong, Singapore (Singapore), United States(San Francisco) and Germany (Frankfurt). OmniEdge is expanding and adding more more servers accordingly. 

OmniEdge clients selects the nearly supernode automatically for low latency. 

# Why run your own Supernode Server? 

Basically you never need to run your own supernode server. There are 2 main reasons you can consider: 

1. For higher speed and for lower latency
2. For policy compliance

## For higher speed and for lower latency

Your nodes may be located far from an existing Supernode Server, finding high latency connecting to the default supernode servers and low speed between nodes. 

If you lived in a place where we don't run the supernode server or in Argentina, you may use the default supernode in the United States(San Francisco), experience high latency to the omniedge's supernode server and lower speed between your nodes which are near you. 

A customize supernode will help you speed up the connections.

## For policy compliance

The default supernode servers are shared across customers, but only help you build peer-to-peer connections and relay your encrypted traffic if p2p connection failed. OmniEdge can't see or decrypt your traffic. 

If you care more abut the traffic, run your own supernode will be the great solution. You are fully control of your supernode server. 

** Once your own supernode server is set, the default server will be removed automatically**

# Setup up customize supernode with Docker

## Clone the repo

``` bash
git clone https://github.com/omniedgeio/docker-customize-supernode.git
```

## Build Supernode

```
cd docker-customize-supernode
docker build -t docker-customize-supernode .
```

## Run Supernode

```
docker run -d -p 5565:5565/udp docker-customize-supernode
```

By default, OmniEdge's default supernode run on port UDP(7787), and UDP(5565) for customize supernode, you can use any port you want. 


# Setting in the Omniedge Dashboard

Login in your OmniEdge account, and fill your server IP and port in the dashboard.

![](/assets/docs/OmniEdge-CustomizeAuthServer.png)


-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).