---
title: Build and Secure Hybrid Cloud with OmniEdge
route: Doc / Cases / Hybrid Cloud 
description: A cheap and secure hybrid cloud solution, building private hybrid cloud with expensive public Cloud, affordable Cloud and Edge Computing.
thumbnail: /assets/docs/case-hybrid-cloud-virtual-network.png
index: 4
---

# Build and Secure Hybrid Cloud with OmniEdge

## What is a hybrid cloud ?

Hybrid cloud is a mixed computing cloud service. It is made of on-premises datacenter or private cloud in enterprise own data center, or multiply edge Computing and a public cloud like AWS, Azure, Google and Oracle in their datacenter. The definition is quite similar by the public cloud suppliers: 

**AWS**: [A hybrid cloud](https://aws.amazon.com/hybrid/) is a mixture among the cloud, on premises, and at the edge.

**Microsoft Azure**:  [A hybrid cloud—sometimes](https://azure.microsoft.com/en-us/overview/what-is-hybrid-cloud-computing/) called a cloud hybrid—is a computing environment that combines an on-premises datacenter (also called a private cloud) with a public cloud, allowing data and applications to be shared between them. Some people define hybrid cloud to include “multicloud” configurations where an organization uses more than one public cloud in addition to their on-premises datacenter.

**Google Cloud**: [A hybrid cloud](https://cloud.google.com/learn/what-is-hybrid-cloud) is one in which applications are running in a combination of different environments. Hybrid cloud computing approaches are widespread because almost no one today relies entirely on the public cloud. 

**IBM**: [Hybrid cloud](https://www.ibm.com/cloud/learn/hybrid-cloud) combines and unifies public cloud, private cloud and on-premises infrastructure to create a single, flexible, cost-optimal IT infrastructure.

## benefit 

The most attractive to use hybrid cloud is the great ROI, nearly [76% of Companies are Adopting Multicloud and Hybrid Cloud Approaches](https://www.oracle.com/cloud/oracle-451-research-advisory/) according to Oracle. Besides this, there are benefits like [Effective application governance](https://cloud.google.com/learn/what-is-hybrid-cloud#section-3), Improved performance and reduced latency, Flexible operations. 


## Build hybrid cloud with OmniEdge

### 1. Create an OmniEdge account

+ Sign up your account: [Sign up](https://omniedge.io/register)

### 2. Create Hybrid Cloud Virtual Network

![](/assets/docs/case-hybrid-cloud-virtual-network.png)

Go to [OmniEdge Dashboard](/dashboard)
You can create a hybrid cloud Virtual Network by simplifying click **+ Network**, put name of `Hybrid Cloud Network` and IP Range, we strongly recommend you use the Private IPv4 Addresses: 10.0.0.0 – 10.255.255.255, 172.16.0.0 – 172.31.255.255 and 192.168.0.0 – 192.168.255.255. Here we use **100.100.100.0/24**. 

### 3. Setup customize supernode for the Hybrid virtual network

You can setup your own Supernode server to increase security and speed for your Virtual Network.

Follow the [Customize Supernode Installation](/docs/article/install/customize-supernode) instruction to install the customize supernode on one of your public cloud, open the related port,here with `5565`, you can use any port you want. Put the IP and port into the virtual network setting page, see picture in item 2. 

### 4. Create your own Cloud instance on public Cloud. 

No matter what public cloud service your are using now, create the Cloud Instance by following their instruction. The giant public cloud service like [AWS](https://aws.amazon.com),[Azure](https://azure.microsoft.com), [Google Cloud](http://cloud.google.com), [IBM Cloud](https://www.ibm.com/cloud), [Alibaba Cloud](https://www.aliyun.com), [Oracle Cloud](https://www.oracle.com/cloud/), or affordable Cloud service like [vultr](https://www.vultr.com), [digitalocean](https://www.digitalocean.com), they all provide detailed manuals creating linux based, windows based or macOS based Cloud instances, just choose the one you want. 

### 5. Prepare your on-premise datacenter, Edge Computing, etc

You may need to assemble the server, or edge computing by yourself, install the OS(Linux, macOS or Windows), and connect them to the internet. 


### 6. Install OmniEdge cli on Linux OS, Windows, or MacOS

Install OmniEdge clients on your own hybrid clouds, choose the right one related to the OS. You can read the [OmniEdge Installation Instruction](/docs/article/install) for the details. Here we take Linux for example: 

+ Download and install OmniEdge cli by running the following command:

``` bash
curl https://omniedge.io/install/omniedge-install.sh | bash
```

+ Login By Secret-Key, You can generate secret-key on [OmniEdge web](https://omniedge.io/dashboard)

```bash
omniedge login -s yoursecuritykey
```

+ Join Your Network,you can just call omniedge join, it will automatically prompt the available network for you to choose. And you can also add one parameter `-n` to specify the network id manually. And then, enjoy the omniedge network.

```bash
sudo omniedge join
```
and select the hybrid cloud virtual network

+ Wait a second and a secure VPN will be established
![](/assets/download/OmniEdge-CLI-0.2.0.gif)

```
Each the cloud instance, edge computing, and device which is joined to the `Hybrid cloud virtual network` will be allocated a fixed IP, with this IP, users in the virtual network will have access to the resource.
```

## Secure public Cloud for the hybrid cloud
By limiting the allowed IP on the public cloud, we can hide the public IP. We take AWS cloud for example here. 

Log into your AWS EC2 Console, select your windows EC2, and change the security group setting, in the Edit Inbounds rules setting,change the source for RDP from 0.0.0.0/0 to 100.100.0.0/24.

```
The source CIDR blocks are 0.0.0.0/0 means every IP is allowed to connect to the EC2. While 100.100.0.0/24 limit the connection access from 100.100.0.0 to 100.100.0.254 IP ranges.
```

![](/assets/docs/case-AWS-Security-Groups.png)


## Access your service running on hybrid cloud with different devices

All the team members can access the service with its private IP address running on the hybrid cloud, by invited by the admin to the hybrid cloud network, and install the OmniEdge apps on [macOS, windows, android and iPhone](/download).


Enjoy !!
