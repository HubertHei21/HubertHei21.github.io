---
title: About
author: Hubert
date: 2023-01-30
category: Jekyll
layout: post
---

### 说明

> :warning:  不保证文章内容正确 :exclamation: \
> :warning:  资料来源网络，侵删 :exclamation:

-

> ![GitHub](https://img.shields.io/badge/GitHub-blue.svg?style=social&logo=github) \
> [Template: Jekyll-gitbook](https://sighingnow.github.io/jekyll-gitbook)

-

---

### 配置

[教程](https://www.bilibili.com/video/BV1Ki4y1E7NX?p=1)

### 安装Ruby

[RubyInstaller](https://www.rubyinstaller.org/downloads/)

### 安装Jekyll

```shell
jekyll new myblog
cd myblog
jekyll serve

bundle exec jekyll serve
```

### 预览

<http://127.0.0.1:4000/>

### Config

```yml
title: HI Blogs  # 标题
email: HuberHei21@gmail.com #邮箱
description: >- # 说明
  my blog
baseurl: "" # 仓库名 myblog
url: "" # 域名
twitter_username: 
github_username: HubertHei21

# Build settings
theme: minima #主题
plugins: #插件
  - jekyll-feed
```

### 文件名

yyyy-mm-dd-Title.md

### Header

```md
---
layout: post  #布局
title: "1.配置"  #标题
data: 2023-1-29 12:00 #时间
categories: Jekyll  #分类
permalink: /about/  #永久链接
---
```

### 其他

> :link:
> [jekyll-docs](https://jekyllrb.com/docs/home) \
> [Markdown Emoji](https://www.webfx.com/tools/emoji-cheat-sheet/)
