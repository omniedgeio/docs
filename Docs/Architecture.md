---
title: Architecture 
description: The architecture of OmniEdge, How OmniEdge creates private network.
route: Doc / Architecture
index: 1
thumbnail: /assets/posts-images/how-omniedge-works-main-architecture.png
---
# Architecture 

We designed and developed OmniEdge based upon the following objectives. Simple enough to use for both users and network administrators. Based on the Zero-trust security model. Users can establish a strictly secure network through authentication services such as Okta, G Suite, etc.
Try using peer-to-peer communication instead of relaying nodes to increase the network speed and reduce the risks of single-point failures.

For the above design goals, we get inspired by an open-source VPN software: n2n, and designed the main architecture of OmniEdge.
![](/assets/posts-images/how-omniedge-works-main-architecture.png)

Our architecture has the following components:

## Super Node

Coordinates the communication between nodes within the virtual network.

- Coordinate the traffic transferring between nodes.
- Try to establish a direct peer-to-peer between nodes if possible; otherwise, relay traffic between nodes if there is any firewall.

## Node

An entity within the virtual network is a proxy for devices to access the virtual network.
Keep and manage virtual local information such as keys, network node public keys, etc.
Forward TCP and UDP traffic over the virtual network, either directly or indirectly.
Provide local DNS resolution for proxied requests.

## Manager

The orchestrator of the virtual network
Manage network node data, including device IDs, public keys, IP data, gateways, routing tables, and other information.
Verify nodes and return network data to nodes.
Coordinate changes to the virtual network such as joining and deleting nodes.
Maintain the life cycle of nodes.
Interact with the user authentication service and manages the ACL information of the nodes.

## Client

The tool used by users to access the virtual network
Communicate with nodes and configure and manage nodes.
Handle user registration and login procedure.


-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).