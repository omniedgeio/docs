---
title: frp/ngrok vs. OmniEdge
route: Doc / Compare / Frp-ngrok Vs. OmniEdge
index: 5
description: What is the difference between frp, ngrok and OmniEdge
thumbnail: /assets/OmniEdge-VPN.svg
---

# frp/ngrok vs. OmniEdge

ngrok/frp is a reverse proxy tool used for exposing your local service to the public, let you access your computer's localhost from a mobile device for example. ngrok is a free/paid service. The free service has limitations of requests per minute and only one tunnel at a time. frp is an open-source version of ngrok. 

## The big difference

- Ngrok/frp is limited to TCP webservice only, and you need to set each service before using it.

- OmniEdge is not limited to TCP and covers all the TCP and UDP services, you can access your own devices only by one fixed IP. 

Let's compare some use cases between ngrok/frp and omniedge.

|Use Cases|ngrok/frp|OmniEdge|
|--|--|--|
|**Expose local web service**|`ngrok tcp 3000` then use a public IP like: `https://greatlocalservice.ngrok.io:5565` | `http://100.100.1.1:3000`|
|**SSH**| 22 is your ssh port and 11111 is the reversed port by ngrok `ngrok tcp 22 && ssh admin@greatlocalservice.ngrok.io -p 11111` | `ssh admin@100.100.1.1` |
|**RDP**| `ngrok tcp 3389` and use `greatlocalservice.ngrok.io:15678` for RDP address | Just put the omniedge IP `100.100.1.1` into the RDP Client|
|**FTP**| `ngrok tcp 21 && ftp://greatlocalservice.ngrok.io:8877` | `ftp://100.100.1.1` |
|**VNC**|`ngrok tcp 5900` and use the `greatlocalservice.ngrok.io:9988` as the VNC address |just put the OmniEdge IP `100.100.1.1` into the VNC client|

## Security

|Accessiable|ngrok/frp|OmniEdge|
|-|---|--|
|Accessiable by default|public with free plan|Private automatically|
|Accessiable Limitation|Manually IP whitelisting setting with paid plan|Private automatically|

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).