---
title: Customize Supernode Installation
description: OmniEdge offers customize supernode, You can setup your own Supernode server to increase security and speed for your Private Network.
route: Docs / Install / Customize Supernode
index: 3
thumbnail: /assets/docs/OmniEdge-CustomizeAuthServer.png
---

# Customize Supernode Installation

OmniEdge offers customize supernode, You can setup your own Supernode server to increase security and speed for your Virtual Network.

## Setup up customize supernode with Docker

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

## Setting in the Omniedge Dashboard

Login in your OmniEdge account, and fill your server IP and port in the dashboard.

![](/assets/docs/OmniEdge-CustomizeAuthServer.png)



-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).