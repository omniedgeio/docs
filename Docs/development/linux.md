---
title: Build OmniEdge for Linux
description: OmniEdge is building with a lot of open source projects,and open source as well.
route: Doc / build-linux
index: 8
thumbnail: 
---

# Build OmniEdge for Linux

## Install golang for your distribution

Follow the [instruction](https://go.dev/doc/install) to install golang, we use **1.16.6**, or running the following command:

```bash
wget https://go.dev/dl/go1.16.6.linux-amd64.tar.gz
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.16.6.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
go version
```


## Build for Ubuntu 18.04, 20.04, 22.04/Debian 10, 11

```bash
sudo -E apt-get -y update
sudo -E apt-get install -y openssl
sudo -E apt-get install -y build-essential
sudo -E apt-get install -y libssl-dev
sudo -E apt-get install -y zip
git clone https://github.com/omniedgeio/omniedge-cli
cd omniedge-cli
go mod download
go generate
BUILD_ENV=prod make build
```

## Build for Fedora 36, CentOS 8

```bash
sudo yum update
sudo yum -y install gcc-c++ curl wget zip wget git openssl-devel net-tools automake autoconf make
git clone https://github.com/omniedgeio/omniedge-cli
cd omniedge-cli
go mod download
go generate
chmod +x internal/make
BUILD_ENV=prod make build
```



## Build for Arch(Manjaro)

```bash
sudo pacman -Syu --needed unzip git gcc curl wget zip make pkg-config openssl net-tools automake autoconf make
git clone https://github.com/omniedgeio/omniedge-cli
cd omniedge-cli
go mod download
go generate
chmod +x internal/make
BUILD_ENV=prod make build
```

## Build for OpenSuse

```bash
sudo zypper update 
sudo zypper install unzip git gcc curl wget zip make pkg-config openssl net-tools automake autoconf make tar
git clone https://github.com/omniedgeio/omniedge-cli
cd omniedge-cli
go mod download
go generate
chmod +x internal/make
BUILD_ENV=prod make build
```



The compiled omniedge-cli will be found in **/out/**

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).
