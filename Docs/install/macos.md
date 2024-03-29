---
title: Install Omniedge on MacOS
description: OmniEdge MacOS GUI is compatible with M1/M2 MacBook, Cli is compatible with intel MacBook, macOS 10 or later, connect to private network.
route: Doc / Install / MacOS
index: 3
thumbnail: /assets/OmniEdgeall0.5.png
---
# Installing on MacOS

## For M1/M2 user: 

OmniEdge MacOS GUI is compatible with M1/M2 MacBook, macOS 12 or later. Last update: Version 1.0.17, June,22,2022

[Download from App Store](https://apps.apple.com/us/app/omniedgenew/id1603005893)

## For Intel MacBook or experts who want to use CLi

OmniEdge MacOS Cli is compatible with intel Macbook, macOS 10 or later. Last update: Version 0.2.3, April,25, 2022.

*To use OmniEdge on MacOS, please instal Tun/Tap Driver first*

## Install Tun/Tap Driver:

## For Intel Mac: 

  - Download tuntap driver from [https://sourceforge.net/projects/tuntaposx/files/latest/download](https://sourceforge.net/projects/tuntaposx/files/latest/download) 
  - Extract `tuntap_20150118.tar.gz` and Install tuntap by running **tuntap_20150118.pkg**
  - Run `sudo kextload /Library/Extensions/tap.kext` in the terminal

## For M1 Mac user: 

### Fast installation
  - Download and install [Tunnelblick](https://github.com/Tunnelblick/Tunnelblick/releases), install the tun/tap driver with the built-in script.

  ![Tuntap installation](/docs/tuntap-by-tunnelblick.jpg)

### Slow but clean installation

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
- Run `sudo kextload /Library/Extensions/tap.kext` in the terminal
- restart Mac after allowing the security check. 


## Use OmniEdge cli on MacOS

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


If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).