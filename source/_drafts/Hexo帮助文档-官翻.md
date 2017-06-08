---
title: Hexo帮助文档-官翻
date: 2017-06-06 15:12:34
tags: [Hexo,Blog]
categories: [skills]
comments: true
keywords: Hexo, Blog
description: 记录Hexo的学习以及使用中的问题
---
>- 记录Hexo的学习以及使用中的问题
<!-- more -->

# 开始使用

## 概述

### 什么是Hexo?
- Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页

### Hexo的安装
- 安装 Hexo 只需几分钟时间，若您在安装过程中遇到问题或无法找到解决方式，请提交问题，我会尽力解决您的问题

#### 安装前提
- 安装 Hexo 相当简单。然而在安装前，您必须检查电脑中是否已安装下列应用程序：
>- [Node.js](http://www.icoder.xin "Node.js的学习使用")
>- [Git](http://www.icoder.xin "Git的学习使用")
- 在gitbash中使用使用 npm 即可完成 Hexo 的安装
>- $ npm install -g hexo-cli

## 建站
- 安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件
```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
- 新建完成后，指定文件夹的目录如下：
```
.
├── _config.yml ->全局配置文件
├── package.json
├── scaffolds ->模板文件夹
├── source ->源文件存放处
|   ├── _drafts ->草稿
|   └── _posts ->正式发布文件
└── themes ->主题存放处
```

### 全局配置文件
- [_config.yml](http://www.icoderxin "Hexo的全局配置文件") :网站的配置信息，您可以在此配置大部分的参数

### 应用程序信息
- package.json :EJS, Stylus 和 Markdown renderer 已默认安装，您可以自由移除
```
package.json
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^3.0.0",
    "hexo-generator-archive": "^0.1.0",
    "hexo-generator-category": "^0.1.0",
    "hexo-generator-index": "^0.1.0",
    "hexo-generator-tag": "^0.1.0",
    "hexo-renderer-ejs": "^0.1.0",
    "hexo-renderer-stylus": "^0.2.0",
    "hexo-renderer-marked": "^0.2.4",
    "hexo-server": "^0.1.2"
  }
}
```

### 模板文件夹
- 模版文件夹 :当您新建文章时，Hexo 会根据 scaffold 来建立文件。
- Hexo的模板是指在新建的markdown文件中默认填充的内容。例如，如果您修改scaffold/post.md中的Front-matter内容，那么每次新建一篇文章时都会包含这个修改

### 资源文件夹
### 主题文件夹
