---
title: Cross compile OmniEdge 
description: OmniEdge is building with a lot of open source projects,and open source as well.
route: Doc / cross-build
index: 8
thumbnail: 
---

# Cross compile 

## Cross compile OmniEdge for RISC-V64

**Host OS:** Ubuntu 20.04

```bash
apt-get update
apt-get install -y openssl autoconf build-essential libssl-dev zip wget g++-riscv64-linux-gnu gcc-riscv64-linux-gnu

wget https://go.dev/dl/go1.18.4.linux-amd64.tar.gz
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.4.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
go version
export GOOS=linux
export GOARCH=riscv64
export CGO_ENABLED=1
export CC=riscv64-linux-gnu-gcc
git clone https://github.com/omniedgeio/omniedge-cli.git
cd omniedge-cli
go mod download
go generate
BUILD_ENV=prod make build-riscv64
```


The compiled omniedge-cli will be found in **/out/**

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).