---
title: Build OmniEdge for FreeBSD
description: OmniEdge is building with a lot of open source projects,and open source as well.
route: Doc / build-freebsd 
index: 8
thumbnail: 
---

# Build OmniEdge for FreeBSD

## Install golang for your distribution

Follow the [instruction](https://go.dev/doc/install) to install golang, we use **1.16.6**, or running the following command:

```bash
wget https://go.dev/dl/go1.16.6.linux-amd64.tar.gz
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.16.6.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
go version
```

## Build for FreeBSD

```bash
su
pkg update && pkg install go gmake git openssl zip autoconf automake libtool
git clone https://github.com/omniedgeio/omniedge-cli
cd omniedge-cli
go mod download
go generate
BUILD_ENV=prod make build-freebsd
```

The compiled omniedge-cli will be found in **/out/**

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).