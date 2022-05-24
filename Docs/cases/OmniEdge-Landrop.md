---
title: Air Drop Any Files between MacOS, Windows, Routers, Linux and Android with Omniedge from anywhere
route: Doc / Cases / LanDrop
description: Use cases with OmniEdge, Drop any files in your private network without devices limitation
thumbnail: /assets/docs/Case-OmniEdge-LanDrop.jpg
index: 4
---

# Air Drop Any Files between MacOS, Windows, Routers, Linux and Android with Omniedge from anywhere

[LANDrop](https://landrop.app), is an application provides drop any files to any devices on your LAN,  No need to use instant messaging for that anymore. It works on GNU/Linux, Windows, macOS, iOS and Android. 

With [OmniEdge](https://omniedge.io/download), LANDrop can have a wonderful feature, drop files to remote devices over OmniEdge's peer-to-peer network from anywhere. 


![](/assets/docs/Case-OmniEdge-LanDrop.jpg)

Scrcpy's features include:

- Intuitive UI. You know how to use it when you see it.
- Secure. Uses state-of-the-art cryptography algorithm. No one else can see your files.
- No Compression.Doesn't compress your photos and videos when sending.
- And More

## Requirements

- Install LANDrop for your Devices, Download Here: [https://github.com/LANDrop/LANDrop-releases](https://github.com/LANDrop/LANDrop-releases)
- Install OmniEdge for your [macOS](https://omniedge.io/download/macOS), [linux](https://omniedge.io/download/linuxcli), or [windows](https://omniedge.io/download/windows), and on your [android](https://omniedge.io/download/android) devices. Read the [OmniEdge Installation Instruction](https://omniedge.io/docs/article/Install) to install OmniEdge. The below example is on macOS and Android. Air Drop files between macOS and Android.

## Install LANDrop for Android and macOS

### Install LANDrop for macOS

Download macOS LANDrop from [LANDrop macOS](https://github.com/LANDrop/LANDrop/releases/download/v0.4.0/LANDrop-0.4.0-macos.dmg), the latest version is 0.4.0. 

Install and run it after downloading. 

### Install LANDrop for Android

Download macOS LANDrop from [LANDrop Android](https://releases.landrop.app/LANDrop-flutter-latest-android.apk), the latest version is 0.4.0. 

Install and run it after downloading. 

![](/assets/docs/Case-LANDrop-Setting.png)

## Install OmniEdge for MacOS

OmniEdge MacOS Cli is compatible with intel Macbook, macOS 10 or later Last update: Version 0.2.2, February 27, 2022.

*To use OmniEdge on MacOS, please instal Tun/Tap Driver first*

### Install Tun/Tap Driver:

#### For Intel Mac: 

  - Download tuntap driver from [https://sourceforge.net/projects/tuntaposx/files/latest/download](https://sourceforge.net/projects/tuntaposx/files/latest/download) 
  - Extract `tuntap_20150118.tar.gz` and Install tuntap by running **tuntap_20150118.pkg**

#### For M1 Mac user: 

  - Download `https://github.com/Tunnelblick/Tunnelblick/tree/master/third_party/tap-notarized.kext`
  - Download `https://github.com/Tunnelblick/Tunnelblick/tree/master/third_party/tun-notarized.kext`
  - Change the name to **tap.kext** and **tap.kext**, 
  - Copy to **/Library/Extensions**
  - add `net.tunnelblick.tap.plist` and `net.tunnelblick.tun.plist` to `/Library/LaunchDaemons/`

  ```bash
    #net.tunnelblick.tap.plist
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>net.tunnelblick.tap</string>
        <key>ProgramArguments</key>
        <array>
            <string>/sbin/kextload</string>
            <string>/Library/Extensions/tap.kext</string>
        </array>
        <key>KeepAlive</key>
        <false/>
        <key>RunAtLoad</key>
        <true/>
        <key>UserName</key>
        <string>root</string>
    </dict>
    </plist>

  ```

  ```bash
    #net.tunnelblick.tun.plist
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>net.tunnelblick.tun</string>
        <key>ProgramArguments</key>
        <array>
            <string>/sbin/kextload</string>
            <string>/Library/Extensions/tun.kext</string>
        </array>
        <key>KeepAlive</key>
        <false/>
        <key>RunAtLoad</key>
        <true/>
        <key>UserName</key>
        <string>root</string>
    </dict>
    </plist>
  ```
- restart Mac after allowing the security check. 


### Use OmniEdge cli on MacOS

+ Sign up your account: [Sign up](https://omniedge.io/register)

+ Download and install omnidge cli by running the following command:

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

with a speicified virtual network.

+ Wait a second and a secure VPN will be established
![](/assets/download/OmniEdge-CLI-0.2.0.gif)


## Installing OmniEdge on Android

OmniEdge Android is compatible with Android 6 or later mobile phone or TV. Last update: Version 0.2.2, March 21,2022.

[Download for Android 6 or later](/install/download/0.2.2/omniedge-release-v0.2.2.apk)

+ Download OmniEdge APK and install it
+ Run OmniEdge and Sign in with your email address
+ Click the connect button
+ Allow installing a VPN configuration
+ Enjoy the secure VPN connection

## Drop Files between Android and macOS

Open LANDrop on Android and macOS, you will see your Android Phone from your macOS, your macbook pro from Android. Select fiels and send them. 

![](/assets/docs/Case-OmniEdge-LanDrop.jpg)

Enjoy !!

-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).