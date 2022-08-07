---
title: Install OmniEdge Linux Cli
description: OmniEdge Linux Cli is Compatible with linux for AMD64,Apple M1, Intel X86, ArmV7 and Arm64V8, connect to private network.
route: Doc / Install / Linux Cli
index: 3
thumbnail: /assets/OmniEdgeall0.5.png
---

# Installing on Linux

OmniEdge Linux Cli is Compatible with macOS and linux for AMD64,Apple M1, Intel X86, ArmV7 and Arm64V8, Last update: Version 0.2.3, April 25, 2022.

+ Sign up your account: [Sign up](https://omniedge.io/register)

+ Download and install OmniEdge cli by running the following command:

``` bash
curl https://omniedge.io/install/omniedge-install.sh | bash
```

+ Login By Password:

``` bash
omniedge login -u yourname@youremail.com -f your_auth_file_path
```
+ Login By Secret-Key, You can generate secret-key on [omniedge web](https://omniedge.io/dashboard)

```bash
omniedge login -s yoursecuritykey -f your_auth_file_path
```

+ Join Your Network,you can just call omniedge join, it will automatically prompt the available network for you to choose. And you can also add one parameter `-n` to specify the network id manually. And then, enjoy the omniedge network.

```bash
sudo omniedge join -f your_auth_file_path
```
and select your virtual network or

``` bash
sudo omniedge join -n 'virtual-network-id'
```

with a specified virtual network.

+ Wait a second and a secure VPN will be established
![omniedge cli ](/assets/download/OmniEdge-CLI-0.2.0.gif)


-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).