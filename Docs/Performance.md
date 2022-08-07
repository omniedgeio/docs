---
title: Performance
description: To solve all the above issues, we designed and developed OmniEdge based upon the following objectives.Simple enough to use for both users and network administrators.Based on the Zero-trust security model. Users can establish a strictly secure network through authentication services such as Okta, G Suite, etc.
route: Doc / Performance
index: 1
thumbnail: /assets/posts-images/how-omniedge-works-main-architecture.png
---

# OmniEdge Performance Measurement

## Test Setup

Test test runs between 2 AWS EC2 nodes type `t2.micro` and `m5.large` in `us-east-2`.

The nodes specifications :

## t2.micro
```
Intel® Xeon® Scalable Processors
1 vCPUs
1 GiB Ram
Low to Moderate
OS: AWS Linux 2 AMI
```
## m5.large 

```
Intel Xeon Platinum 8000 CPU (64 bit)
2 vCPUs
8 GiB Ram
Up to 10 Gbps network
OS: AWS Linux 2 AMI
```

## Test tools: 

- [iperf3](https://iperf.fr/iperf-download.php)

## OmniEdge Version
- OmniEdge Evaluation version 0.1.0
- OmniEdge 1.0 (internal developmen)


## Throughput on t2.micro

|Through put test|Bandwidth|
|--|--|
|Native Network|1090 Mbit/s|
|OmniEdge Evalution|170 Mbit/s|
|OmniEdge 1.0|247 Mbit/s|


## Throughput on m5.large

|Through put test|Bandwidth|
|--|--|
|Native Network|4970 Mbit/s|
|OmniEdge Evalution|554 Mbit/s|
|OmniEdge 1.0|3470 Mbit/s|


## Conclusion

- The OmniEdge Evaluation can reach 554 Mbit/s.
- The new OmniEdge version can reach 3470 Mbit/s. 

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).