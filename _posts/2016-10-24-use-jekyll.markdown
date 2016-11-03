---
layout: post
title:  采用jekyll搭建markdown静态博客
date:   2016-10-24 17:21:08 +0800
categories: yuu
tags: markdown jekyll
---

## 0. 文章概要

- macos下安装jekyll
- 发布博客文章
- 配置博客网站
- 发布到github

## 1. 安装jekyll

### 1.1 本文环境

- MacOS 10.12
- 安装 Xcode Command-Line Tools

### 1.2 软件环境

- [Ruby](http://www.ruby-lang.org/en/downloads/ "Ruby")
- [Rubygems](https://rubygems.org/pages/download "Rubygems")

### 1.3 安装

- 安装 jekyll
```
gem install jekyll
```

- 创建博客网站模板
```
jekyll new myblog
```

- 进入目录
```
cd myblog
```

- 运行
```
jekyll serve
```
![jekyll serve](http://oflimcy5e.bkt.clouddn.com/jekyll-server.png "jekyll serve")

- 在浏览器中输入 http://localhost:4000
![jekyll serve](http://oflimcy5e.bkt.clouddn.com/jekyll-server-browse.png "jekyll serve")

## 2. 撰写博客

### 2.1 文件名规范

- 文件在 _posts 目录下

- 文件名格式 年-月-日-标题.MARKUP
```
2016-10-24-welcome-to-jekyll.markdown
```

### 2.2 文章格式

- 先打开默写文件看下 _posts/2016-10-24-welcome-to-jekyll.markdown

- `头信息`配置如下
    - layout 模板
    - title 标题
    - date 时间
    - categories 分类目录 空格子目录
    - category 目录
    - tags 标签

```
---
layout: post
title:  "Welcome to Jekyll!"
date:   2016-10-24 16:21:08 +0800
categories: jekyll update
category: aaa 
tags: bbb ccc
---

Jekyll文章正文

```

### 2.3 浏览查看

- url变化 , 规则 = categories + category + 年月日 + 标题
```
http://127.0.0.1:4000/jekyll/update/aaa/2016/10/24/welcome-to-jekyll.html
```

- 浏览

![jekyll serve](http://oflimcy5e.bkt.clouddn.com/jekyll-blog.png "jekyll serve")

## 3. 配置网站

### 3.1 修改基础属性

- 编辑 _config.yml , 自己看着改就行

```
title: 剑九的博客
email: tao.hans@gmail.com
description: > # 关注 ios xcode 代码架构
baseurl: "" # the subpath of your site, e.g. /blog
url: "" # the base hostname & protocol for your site, e.g. http://example.com
twitter_username: hanstwitter
github_username:  hansgithub

# Build settings
markdown: kramdown
theme: minima
gems:
  - jekyll-feed
exclude:
  - Gemfile
  - Gemfile.lock
```

### 3.1 页面 url 格式

- 默认的 url 太长，你可以自己改下
- 加入配置项目 `permalink` 我去掉了 天

```
permalink: /:categories/:year/:month/:title.html
```

### 3.2 套用模板




# 配置网站

- 修改配置文件 _config.yml , 大家可以自己打开看下

# 撰写博客

- _posts 目录就是你的博客文了

- 文档格式 年-月-日-标题.MARKUP ，参考下 目录下的文件名

- 打开系统生成的文件看下 年-月-日-welcome-to-jekyll

    - 第一部分 头信息
```
---
layout: post 模板
title:  "Welcome to Jekyll!" 标题
date:   2016-10-24 16:21:08 +0800 时间
categories: jekyll update 分类目录 空格子目录
category: 目录
tags: 标签
---
```

    - 第二部分 正文
```
markdown 格式
```

- 执行 jekyll build 生成文章到 _site 目录

- 或者执行 jekyll server 一边编辑一边查看

# 安装过程中出现的问题

- 错误1: kernel_require.rb:55:in `require': cannot load such file -- bundler

```
- 需要安装 bundler
gem install bundler
bundle install
```

- 错误2: Errno::EACCES

```
- 都是因为没有权限
sudo xxx
```

# 参考文档

> [Jekyll 的全面指南](http://jekyll.com.cn/docs/home/ "Jekyll 的全面指南")
