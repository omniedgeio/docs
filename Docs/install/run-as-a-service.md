---
title: Run OmniEdge as a Service
description: OmniEdge can start automatically in your devices With the function run omniedge as a service, with the function of refresh token, you don't need to rejoin again, which is helpful for unattended devices. 
route: Doc / Install / Run OmniEdge as a service
index: 3
thumbnail: /assets/docs/install-run-omniedge-as-a-service.png
---

# Run OmniEdge as a Service

OmniEdge can start automatically in your devices With the function run omniedge as a service, with the function of refresh token, you don't need to rejoin again, which is helpful for unattended devices. 

`Refresh token is available from version 0.2.3`

| ![Run OmniEdge as a Service](/assets/docs/install-run-omniedge-as-a-service.png) |
|:--:|
| <b>Run OmniEdge as a Service</b>|

## Get virtual network ID

After login in omniedge, run the command `omniedge join -f .omniedge/auth.json` to get your virtual network ID.

```bash
omniedge join -f .omniedge/auth.json

INFO[0000] You are in mode: prod
INFO[2022-01-17T11:34:28] List Virtual Network response
Use the arrow keys to navigate: ↓ ↑ → ←  and / toggles search
choose the network
  🌶 Home

--------- Virtual Network ----------
Name:        Home
Cidr:        100.100.0.0/24
Role:        2
ID:          your_virtual_network_id

```

## Create OmniEdge Service 

Change the virtual network and your_auth_file_path and create **omniedge.service**

```bash
vi /etc/systemd/system/omniedge.service
```

```
#/etc/systemd/system/omniedge.service
[Unit]
Description=omniedge process
After=network-online.target syslog.target nfw.target
Wants=network-online.target

[Service]
Type=simple
ExecStartPre=
#Replace to your real virtual network id(can be found by run omniedge join) and auth.json path
ExecStart=/usr/local/bin/omniedge join -n "your_virtual_network_id" -f your_auth_file_path
Restart=on-abnormal
RestartSec=5

[Install]
WantedBy=multi-user.target
Alias=

```

## Activate and start `omniedge.service`

```bash
systemctl daemon-reload
systemctl enable omniedge.service
systemctl start omniedge.service
```

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).