---
title: Installing OmniEdge on Synology
description: OmniEdge Synology is Compatible with ArmV7 and Arm64V8, connect to private network.
route: Doc / Install / Synology
index: 3
thumbnail: /assets/download/omniedge-synology-en.png
---

# Installing on Synology

OmniEdge Synology is Compatible with ArmV7 and Arm64V8, Last update: **Version 0.2.3.3, July 15, 2022**.

[Download from Github](https://github.com/omniedgeio/omniedge-synology/releases)

1. Sign up your account
2. Generate **Security-key**, get the **Virtual Network ID** and **IP Range** from [Dashboard](https://omniedge.io/dashboard)
3. Download and install OmniEdge Synology
4. Fill **Security-key**, **Network ID** and **IP Range** during the installation wizard
5. Special for DSM7, run the command in terminal after installation:

```bash
sudo sed -i 's/package/root/g' /var/packages/omniedge/conf/privilege
```

![](/assets/download/omniedge-synology-en.png)



-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).