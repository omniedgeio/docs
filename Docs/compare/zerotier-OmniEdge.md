---
title: ZeroTier vs. OmniEdge
route: Doc / Compare / ZeroTier vs. OmniEdge
index: 5
description: What is the difference between ZeroTier and OmniEdge
thumbnail: /assets/OmniEdge-VPN.svg
---

# ZeroTier vs. OmniEdge

When more and more enterprise services are migratig to cloud-based services, and people are more likely work from home, which drives the use of VPNs. The security concerns, which means every device should be end-to-end encrypted and authenciated. People want to connect their private resources, devices, from anywhere in a highly security method, and this is what OmniEdge and ZeroTier want to help and come in.


**ZeroTier** is a smart Ethernet switch for planet Earth. It’s a distributed network hypervisor built atop a cryptographically secure global peer to peer network. It provides advanced network virtualization and management capabilities on par with an enterprise SDN switch, but across both local and wide area networks and connecting almost any kind of app or device.[ZeroTier Doc]. In other world, the developer themsevles call ZeroTier "Virtual Distributed Network (VDN) " instead of VPN. It has two virtualization layers: 

- VL1 is the underlying peer to peer transport layer, the “virtual wire,” 
- VL2 is an emulated Ethernet layer that provides operating systems and apps with a familiar communication medium.

**OmniEdge** is a layer-2 peer-to-peer VPN, users can create and manage their own secure and geographically distributed overlay network without the need for central administration. A SaaS central coordination service which is invisible to users. Nodes are logging into a system with Google, and Email/Password. OmniEdge provides several supernode in differnet locations which will be allocated to users. The supernode coordinates the communication between nodes within the virtual network, try to eastablish a direct peer-to-peer between nodes if possible, otherwise, relay traffic between nodes if there is any firwall. Users are allowed to use their [custom supernode](/docs#6-customize-supernode) to improve the security. 


ZeroTier and OmniEdge share a similar purpose but with differenct structures. 

## Setup

ZeroTier is designed to be a “zero-configuration” technology. Users don't need to write configurations or IP address for the nodes, with the help of Virutualization Layer 2 (VL2), new nodes can be added to a Virtual Network by a secret code, which must be entered manually at connection time. 

OmniEdge's desgin is also with "zero-config" logic. The [Dashboard](/docs/article/Admin) will handle all the configurations, IP address and Nodes's name. Users connect their own private network with no concerns, no matter for the first user or the new users. A default private network will be generated automatically, or users can create more private virutal networks for different purpose. The nodes can seclect differenct private work and join, or invite others. 

## Performance

ZeroTier's latency is very low compared to legacy VPNs. The only problems for any peer-to-peer connections is when the connections are completely blocked and the packet has to rely on relaying through the supernode. 

ZeroTier 1.2.3 (pre-1.2.4)'s [benchmarking](https://www.zerotier.com/2017/04/20/benchmarking-zerotier-vs-openvpn-and-linux-ipsec/) is **484 Mbit/sec** using [iperf3](https://iperf.fr/) under a native network with speed **4760 mbps**, which was done by ZeroTier between two single-core Linux (CentOS 7) virtual machines running on VMWare Workstation on the same Core i7 at 2.8ghz. 

OmniEdge has a great latency. The [performance](https://twitter.com/omniedgeio/status/1502653680385896450?s=20&t=EL13zwfh7ps51Rmnxh3deQ) is **9.7ms** with omniedge IP vs. **8ms** with public IP, between AWS EC2 in Osaka and Tokyo. The lantecy can be improved when user use a close custome supernode. OmniEdge also have a good throughput. The [speed](https://omniedge.io/docs/article/Architecture&Performance) can reach to **3470 Mbit/s** under a native network with speed **4970 Mbit/s** between 2 AWS m5.large. 

```
Notice: the throughput test enviroment is different between ZeroTier & Omniedge, so is the result.
```

ZeroTier and OmniEdge are the new alternatives to the legacy VPNs, both are sharing the same purpose to make the connection eaiser.


-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).