---
title: Build OmniEdge for android
description: OmniEdge is building with a lot of open source projects,and open source as well.
route: Doc / build-android 
index: 8
thumbnail: 
---

# Build OmniEdge Android

1. Download Android Studio: https://developer.android.com/studio
2. Get the repo and compile

```bash
git clone https://github.com/omniedgeio/omniedge-android.git`
./gradlew test --stacktrace
./gradlew assembleDebug --stacktrace
```

We have also prepared the CI for Github and Gitlab for building automatically. 

- [Github](https://github.com/omniedgeio/omniedge-android/blob/main/.github/workflows/build.yml)
- [GitLab](https://github.com/omniedgeio/omniedge-android/blob/main/.gitlab-ci.yml)

-----

If you have more questions, feel free to [discuss](https://github.com/omniedgeio/omniedge/discussions).