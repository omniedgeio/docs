# OmniEdge Documentation

[https://omniedge.io/docs](https://omniedge.io/docs)

**The docs are written with specified markdown format, the frontend system will parse them automatically.** 

## How to contribute docs

1. Clone this repo by 
```bash
git clone https://github.com/omniedgeio/docs.git
```
3. Create a new branch from the main by
```bash
git checkout -b doc/articlename main
```
5. Create a markdown file as the format mentioned below in Docs or in the subfolder related
6. Write your content accordingly, copy images you use to the `Images` folder
7. Push the branch to the repo by 
```bash
git add . && git commit -am "doc():add article name" && git push origin doc/articlename
```
10. Create a Pull request from `https://github.com/omniedgeio/docs/pulls`, and waiting for review. 


## The format of the docs

Template docs:

```markdown
---
title: The title of the article
description: The abstract of the article
route: The route of this article, like Doc / OTHERS
index: 5 
thumbnail: path of the thumbnail picture
---
<!-- Content Start -->
# The Head
## The Second Head
<!-- Content End -->

-----

If you have more questions, feel free to [contact us](mailto:support@OmniEdge.io).

```

## Contributors

-----

If you have more questions, feel free to [contact us](mailto:support@OmniEdge.io).
