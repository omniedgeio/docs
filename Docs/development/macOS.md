---
title: Build OmniEdge for macOS
description: OmniEdge is building with a lot of open source projects,and open source as well.
route: Doc / build-macos
index: 8
thumbnail: 
---

# Build OmniEdge for macOS

## OmniEdge-macOS GUI

1. Download and install Xcode
2. Get the repo and compile

```bash
git clone https://github.com/omniedgeio/omniedge-macOS.git
cd omniedge-macOS
open Omniedge.xcodeproj
```

Xcode will open automatically, you have to set your developer account to start the compile.

## OmniEdge-macOS Cli

### Install golang for macOS

Follow the instruction to install golang, we use 1.16.6 here: https://go.dev/doc/install

### Install dependencies and build 

```bash
brew install autoconf automake libtool
git clone https://github.com/omniedgeio/omniedge-cli
cd omniedge-cli
go mod download
go generate
BUILD_ENV=prod make build-darwin
```

The compiled omniedge-cli will be found in **/out/**

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).