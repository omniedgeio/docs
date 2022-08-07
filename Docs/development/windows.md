---
title: Build OmniEdge for windows
description: OmniEdge is building with a lot of open source projects,and open source as well.
route: Doc / build-windows
index: 8
thumbnail: 
---

# Build OmniEdge for Windows

1. Download [QT 5.12.12 for windows](https://download.qt.io/official_releases/qt/5.12/5.12.12/) and [Inno Setup for windows](https://jrsoftware.org/isdl.php#stable)
2. Get the repo and compile

```bash
git clone https://github.com/omniedgeio/omniedge-windows.git
cd omniedge-windows
```

3. open **OmniEdge.pro** and **QT Creator** will open automatically
4. Set the Kits to **Desktop Qt 5.12.12 MSVC2017 32bit**, select build with **Release**, set the Build directory to: `.\build-package\build\`

![](/assets/docs/compile-windows-Kits.png)

![](/assets/docs/compile-windows-release.png)

5. Press `crtl+B` to build, and you will find **OmniEdge.exe** in the folder`.\build-package\build\release\`.
6. copy **OmniEdge.exe** to `.\build-package\package\`,open **omniedge_withTAP_V02_bat.iss** with Inno Setup Compile, press `ctril+F9` to compile and you will find the installer package in the folder `.\build-package\release`


-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).
