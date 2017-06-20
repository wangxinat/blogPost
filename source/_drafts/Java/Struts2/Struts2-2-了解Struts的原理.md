---
title: Struts2_2_了解Struts的原理
tags:
  - Struts2
  - Java开发框架
  - ValueStack
  - OGNL
categories:
  - Java
  - Struts2
keywords: 'Blog,Java,Web,前端,后端,Python,PHP,开发者,程序员,javascript,Html,maven,gitHub,学习分享,编程'
date: 2017-06-08 15:44:13
description: Struts2的学习以及开发实践
---
> 学习Struts2的内部原理
<!-- more -->

## Struts2中的参数传递

### VakueStack值栈
![](http://or5qwkb5l.bkt.clouddn.com/valueStack.jpg)
>ValueStack是Struts2中,Action向页面传递数据的媒介,ValueStack封装了Action的数据,并允许JSP通过OGNL表达式来对其进行访问

#### 访问valueStack
>在页面通过&lt;s:debug/&gt;标签观察其结构,仅供程序员进行代码调试

-  输出栈顶 &lt;s:property/&gt;
```
ValueStack栈顶的变化
      默认情况下栈顶为Action
      循环过程中栈顶为循环变量
          迭代集合时,循环变量是集合中的对象,通常都是实体对象,即:栈顶是实体对象
          按数字迭代时,循环变量是数字,不能用数字为实体对象,通过var声明变量名,根据键值从context中取值
```
- 访问Context对象 :输出context对象数据
```
OGNL表达式以"#"开头
以key来访问context对象的值,通过"#key"获取context中某属性的
值
```
