---
title: Display and control your Android device with Omniedge from anywhere on MacOS, Windows and Linux
route: Doc / Cases 
description: Connect all android devices in your private network, and control remotely
thumbnail: /assets/docs/Scrply-OmniEdge.jpg
index: 4
---

# Display and control your Android device with Omniedge from anywhere on MacOS, Windows and Linux

[Scrcpy, pronounced "screen copy"](https://github.com/Genymobile/scrcpy), is an application provides display and control of Android devices connected via USB (or over TCP/IP). It does not require any root access. It works on GNU/Linux, Windows and macOS. 

With [OmniEdge](https://omniedge.io/download), Scrcpy can have a wonderful feature, remote display and control of android devices over OmniEdge's peer-to-peer network from anywhere. 

![](/assets/docs/Scrply-OmniEdge.jpg)

Scrcpy's features include:

- recording
- mirroring with device screen off
- copy-paste in both directions
- configurable quality
- device screen as a webcam (V4L2) (Linux-only)
- physical keyboard simulation (HID) (Linux-only)
- physical mouse simulation (HID) (Linux-only)
- OTG mode (Linux-only)

## Requirements

- The Android device requires at least API 21 (Android 5.0).
- Make sure you [enabled adb debugging](https://developer.android.com/studio/command-line/adb.html#Enabling) on your device(s).
- On some devices, you also need to enable [an additional option](https://github.com/Genymobile/scrcpy/issues/70#issuecomment-373286323) to control it using keyboard and mouse.
- Install OmniEdge for your [macOS](https://omniedge.io/download/macOS), [linux](https://omniedge.io/download/linuxcli), or [windows](https://omniedge.io/download/windows), and on your [android](https://omniedge.io/download/android) devices. Read the [OmniEdge Installation Instruction](https://omniedge.io/docs/article/Install) to install OmniEdge. The below example is on macOS. 

## Install Scrcpy for macOS

The application is available in Homebrew. Just install it:

``` bash
brew install scrcpy
```

You need adb, accessible from your PATH. If you don't have it yet:

```bash
brew install android-platform-tools
```

## Install OmniEdge for MacOS

OmniEdge MacOS Cli is compatible with intel Macbook, macOS 10 or later Last update: Version 0.2.2, January 15, 2022.

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

OmniEdge Android is compatible with Android 6 or later mobile phone or TV. Last update: Version 0.2.3, July 11,2022.

[Download for Android 6 or later](/install/download/0.2.3/omniedge-release-v0.2.3.apk)

+ Download OmniEdge APK and install it
+ Run OmniEdge and Sign in with your email address
+ Click the connect button
+ Allow installing a VPN configuration
+ Enjoy the secure VPN connection

## Display and control Android with OmniEdge

Run scrcpy in the termial: 
```bash
$scrcpy --tcpip=10.100.100.2:5555
```

Then you will see the following output, and a popup-window will open to show your android device's screen: 

```bash
scrcpy 1.22 <https://github.com/Genymobile/scrcpy>
2022-02-10 17:03:25.249 scrcpy[41700:1349554] INFO: Connected to 10.100.100.2:5555
/opt/homebrew/Cellar/scrcpy/1.22_1/share/scrcpy/scrcpy-server: 1 file pushed, 0 skipped. 15.5 MB/s (40955 bytes in 0.003s)
[server] INFO: Device: OnePlus HD1900 (Android 11)
2022-02-10 17:03:34.824 scrcpy[41700:1349549] INFO: Renderer: metal
2022-02-10 17:03:34.848 scrcpy[41700:1349549] INFO: Initial texture: 1080x2400
2022-02-10 17:05:13.675 scrcpy[41700:1349549] TSM AdjustCapsLockLEDForKeyTransitionHandling - _ISSetPhysicalKeyboardCapsLockLED Inhibit
```

Enjoy !!
