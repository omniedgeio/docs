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

We offer free public supernodes you are using for starter plans, allocated automatically by your registered IP address via GeoIP. You network may be slow if your IP location is different from your devices. But you can [use your own supernode](https://omniedge.io/docs/article/install/customize-supernode) with [pro & team plans](https://omniedge.io/pricing). 

|Location|Cloud Vendor|Specification|Version|
|--|--|--|--|
|Hong Kong,CN|AWS| 2vCPUs / 1GB RAM|2.6-stable-omni|
|Singapore,SG|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Tokyo,JP|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Oregon,US|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Ohio,US|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Mumbai,IN|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Sao Paulo,BR|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Frankfurt,DE|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Milan,IT|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|
|Sydney,AU|AWS|1vCPU / 0.5GB RAM|2.6-stable-omni|

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

# Setup customize supernode 

OmniEdge offers customize supernode, You can setup your own Supernode server to increase security and speed for your Virtual Network, here you can setup a supernode server with docker.

```bash
sudo docker run -d -p 443:443/udp omniedge/supernode:latest
```

# Setting in the Omniedge Dashboard

Login in your OmniEdge account, and fill your server IP and port in the dashboard.

![](/assets/docs/OmniEdge-CustomizeAuthServer.png)


-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).