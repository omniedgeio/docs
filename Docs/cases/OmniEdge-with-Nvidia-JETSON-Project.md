---
title: OmniEdge with Nvidia JETSON Project
route: Doc / Cases / Nvidia Jetson
description: Connect your AI robot into your own private network
thumbnail: /assets/docs/case-aws-windows-2.png
index: 4
---

# OmniEdge with Nvidia JETSON Project

## Tools we need:
- Nvidia JETSON NAND Board
- MicroSD Card 32GB
- MicroSD Card Reader
- Micro-USB Power Supply 5V-2A
- OmniEdge for Linux

## Step 1 
Download the [Jetson Nano Developer Kit SD Card Image](https://developer.nvidia.com/jetson-nano-sd-card-image), and note where it was saved on the computer, unzip it when download is finished:

```bash
unzip -p ~/Downloads/jetson_nano_devkit_sd_card.zip
```

## Step 2 

Write the image to your microSD card on macOS. Herewith the command, you have to use: 

```bash
diskutil list external | fgrep '/dev/disk'
diskutil unmountDisk /dev/disk2
sudo dd if=~/Download/jetson.img of=/dev/rdisk4 bs=1m 
13071+0 records in
13071+0 records out
13705936896 bytes transferred in 691.454329 secs (19821898 bytes/sec)
```
Click `Eject` on the `popup window` when finished 

>Please notice the numder **4** in `/dev/disk4` and `/dev/rdisk4`.

## Step 3 
Insert your Micro-SD card into your Jetson Board, plug the power supply, HDMI to a Monitor, and a USB-Keyboard, power on the board. Finish the system setting, and enter into the ubuntu-desktop. 

## Step 4 
Download and install omnidge cli by running the following command:

``` bash
curl https://omniedge.io/install/omniedge-install.sh | bash
```

## Step 5 

Login OmniEdge and Join Virtual Network

+ Login By Password:

``` bash
omniedge login -u yourname@youremail.com -f your_auth_file_path
```
+ Login By Secret-Key, You can generate secret-key on omniedge web

```bash
omniedge login -s yoursecuritykey -f your_auth_file_path
```

+ Join Your Network,you can just call omniedge join, it will automatically prompt the available network for you to choose. And you can also add one parameter -n to specify the network id manually. And then, enjoy the omniedge network.

```bash
sudo omniedge join -f your_auth_file_path
```
and select your virtual network or

``` bash
sudo omniedge join -n 'virtual-network-id'
```
with a speicified virtual network.

+ Wait a second and a secure VPN will be established

![omniedge cli](/assets/download/OmniEdge-CLI-0.2.0.gif)


## Step 6 
Now your laptop and your Jetson have joined in the same virtual network, you can use `ssh` to connect. 

-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).