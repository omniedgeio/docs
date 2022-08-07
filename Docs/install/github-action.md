---
title: OmniEdge for Github Action
description: Bring Github Action into intranet
route: Doc / Install / OmniEdge for Github Action
index: 3
thumbnail: 
---

# OmniEdge for Github Action

Bring Github Action into intranet, access nodes/devices from CI workflows.

## Usage

```bash
- name: OmniEdge for Github Action
  uses: omniedgeio/github-action@v1
  with:
    securitykey: ${{ secrets.OMNIEDGE_SECURITY_KEY }}
    virtualnetworkid: ${{ secrets.OMNIEDGE_VIRTUALNETWORK_ID }}
```
      
1. [Sign up](https://omniedge.io/register) your account
2. Generate Security-key, and get the Virtual Network ID from [Dashboard](https://omniedge.io/dashboard)
3. Put your own Security-key and Virtual Network ID into your action


## Example

- [Check server status with Github Action without exposing public IP addresses](https://github.com/omniedgeio/server-status)


-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).