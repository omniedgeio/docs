---
title: Installing OmniEdge on Synology
description: OmniEdge Synology is Compatible with ArmV7 and Arm64V8, connect to private network.
route: Doc / Install / Synology
index: 3
thumbnail: /assets/OmniEdgeall0.5.png
---

# Installing on Synology

OmniEdge Synology is Compatible with ArmV7 and Arm64V8, Last update: Version 0.2.3, April 25, 2022.

+ Sign up your account: [Sign up](https://omniedge.io/register)

+ Download and install omniedge synology from: [https://github.com/omniedgeio/omniedge-synology/releases](https://github.com/omniedgeio/omniedge-synology/releases)

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

with a speicified virtual network.

+ Wait a second and a secure VPN will be established
![omniedge cli ](/assets/download/OmniEdge-CLI-0.2.0.gif)


-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).