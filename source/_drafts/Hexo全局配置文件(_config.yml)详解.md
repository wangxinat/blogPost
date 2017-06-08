---
title: Hexo全局配置文件(_config.yml)详解
date: 2017-06-06 11:20:59
tags: [Hexo,Blog]
categories: [skills]
---
## _config.yml :全局配置说明
<!-- more -->
```
# Site 网站相关配置说明
<!-- 博客站点标题,显示在首页上的 -->
title: VanXin`s Blog
<!-- 博客站点副标题 -->
subtitle: 记录工作学习中的点点滴滴
<!-- 博客网站相关描述 -->
description: 私人小站-专注于JavaWeb开发
<!-- 博客站点关键字,便于网络检索 -->
keywords: Java,Web,前端,Python,PHP,开发者,程序员,javascript,Html,maven,gitHub
<!-- 站点拥有者 -->
author: VanXin
<!-- 博客站点语言选项设置 -->
language: zh-CN
email: wangxinat163@163.com
<!-- 时区设置 -->
timezone: Asia/Shanghai

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://www.icoder.xin
root: /
<!-- 文件生成的对应链接地址 -->
# permalink: :year/:month/:day/:title/
permalink: vanxinBlog/:title/
permalink_defaults:

# Directory 文件存放位置相关配置
<!-- 源文件存放位置 -->
source_dir: source
<!-- 公开文件存放位置 :将生成静态网站在这里 -->
public_dir: public
<!-- 标记目录存放位置 -->
tag_dir: tags
<!-- 归档文件目录 -->
archive_dir: archives
<!-- 分类目录 -->
category_dir: categories
<!-- 包括代码目录 -->
code_dir: downloads/code
<!-- i18n目录 -->
i18n_dir: :lang
<!-- 路径不能呈现 -->
skip_render:

# Writing
<!-- 文件默认生成格式 -->
new_post_name: :title.md # File name of new posts
<!-- 默认布局 :发布文件存放在_post -->
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace:

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: MMM D YYYY
<!-- YYYY-MM-DD -->
time_format: HH:mm:ss

# Pagination :分页
## Set per_page to 0 to disable pagination
per_page: 15
pagination_dir: page

# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
<!-- 使用主题 -->
theme: indigo_VanXin
# theme: casual
exclude_generator:
<!-- include	Hexo默认忽略隐藏的文件和文件夹,但设置这个字段将使Hexo过程 -->
<!-- exclude	Hexo过程将忽略文件列表下 -->

# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: git@github.com:vanxinBlog/vanxinBlog.github.io.git
  branch: master

# Archives
## 2: Enable pagination
## 1: Disable pagination
## 0: Fully Disable
archive: 2
category: 2
tag: 2

# Server
## Hexo uses Connect as a server
## You can customize the logger format as defined in
## http://www.senchalabs.org/connect/logger.html
port: 4000
server_ip: localhost
logger: false
logger_format: dev

```
