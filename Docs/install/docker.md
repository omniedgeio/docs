---
title: Run OmniEdge in container
description: Run OmniEdge in container
route: Doc / Install / Docker
index: 3
thumbnail: 
---

# Run OmniEdge in container

Run OmniEdge in container is very easy.

1. Sign up your account
2. Generate **Security-key**, and get the **Virtual Network ID** from [Dashboard](https://omniedge.io/dashboard)
3. Run the command with your own **Security-key** and **Virtual Network ID**:

```bash
sudo docker run -d \
  -e OMNIEDGE_SECURITYKEY=Security-key \
  -e OMNIEDGE_VIRUTALNETWORK_ID="Virtual Network ID" \
  --network host \
  --privileged \
  omniedge/omniedge:latest

```


-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).