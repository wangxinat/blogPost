---
title: Hexo中遇到的问题及解决
tags: [Hexo,Blog]
categories: [skills]
comments: true
keywords: 'Blog,Hexo'
date: 2017-06-06 16:23:14
description: Hexo中遇到的问题及解决
---
- Hexo中遇到的问题及解决
<!-- more -->

## 分类和标签云失效

### 标签的链接设置
```
hexo new page "tags"
编辑tags.md,页面的类型设置为 tags
title: TagCloud
date: 2017-06-06 16:22:17
type: "tags"
layout: tags
```

### 分类的链接设置
 ```
 hexo new page "tags"
 编辑tags.md,页面的类型设置为 tags
 title: categories
 date: 2017-06-06 18:06:04
 layout: categories
 ```

## 评论系统的开启
>- 不知道是使用主题的问题还是什么,友言评论使用不了,改用了网易云跟帖评论
>- 在主题配置文件_config.yml中进行开启,需要先注册一个网易跟帖
![](http://or5qwkb5l.bkt.clouddn.com/comments.png "")

## 指定404错误页面
>- 方法一 :直接在source下创建404.html自定义跳转地址
```
<!DOCTYPE html>
<html lang="en">
  <head>]
  	<meta charset="UTF-8">
  	<title>404</title>
  </head>
  <body>
  	<script type="text/javascript" src="http://www.icoder.xin" charset="utf-8"></script>
  </body>
</html>
```
>- 方法二 :hexo new page 404,在404index.md中可以自己编辑定义显示的内容(暂时空白待自定义)
```
---
title: 404 Not Found
toc: false
reward: false
share: false
comments: false
permalink: /404
---
```
