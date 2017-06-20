---
title: request、session、application、page之间的区别
date: 2017-06-14 09:41:01 星期三
tags:
- Http请求
- Servlet
categories:
- Java
- Servlet
keywords: Blog,Java,Web,前端,后端,Python,PHP,开发者,程序员,javascript,Html,maven,gitHub,学习分享,编程
description:
---
>Web开发过程中经常需要通过Http请求进行服务器和客户端的交互
不可避免得回使用到request、session、application、page等。
<!-- more -->

## 了解几者的生命周期

### 基本概念
| 对象|生效时间|作用域|  实现接口 |
|-|-|-|-|
|request|HTTP请求开始到结束这段时间|在当前请求中有效|HttpServletRequest|
|session|HTTP会话开始到结束这段时间|在当前会话中有效|HttpSession|
|application|服务器启动到停止这段时间|在所有应用程序中有效|ServletContext|
|page|当前页面,在一个jsp页面里有效当前页面|Jsp页面中有效|java.lang.Object|

#### request
>指从http请求到服务器处理结束，返回响应的整个过程。在这个过程中使用forward方式跳转多个jsp。在这些页面里你都可以使用这个变量

```
在一个http的请求周期(见附录1)中都是有效的
可以通过请求转发跳转jsp使用变量,但是只要刷新页面，它们就会失效了,需要重新跳转
```
##### request的实现
>Servlet之间的信息共享是通过HttpServletRequest接口的两个方法来实现的
 - 变量的存放
  - void setAttribute(String name, Object value) ：将对象 value 以 name 为名称保存到request作用域中
  -  Object getAttribute(String name) ：从request作用域中取得指定名字的信息
 - 数据之间的传递
  - doGet()、doPost() 函数的第一个参数就是 HttpServletRequest 对象， 使用这个对象的 setAttribute 即可传递信息。
  - 设置好信息之后，要用到 RequestDispatcher 接口的 forward 方法，将请求转发给其他Servlet

##### 附录1:http请求
>http请求周期 :从http请求发起，到服务器处理结束，返回响应的整个过程.

[========]

#### session
>有效范围当前会话,在第一次请求的时候会话即被开启,有默认的作用时间,浏览器关闭的时候会话结束

```
从用户打开浏览器开始，到用户关闭浏览器这中间的过程。
这个过程可能包含多个请求响应。也就是说，只要用户不关浏览器，服务器就有办法知道这些请求是一个人发起的，整个过程被称为一个会话（session）
放到会话中的变量，就可以在当前会话的所有请求里使用
session和application里的变量一直在累加，开始时候两者作用是相同,当关闭浏览器重启重新访问该页面,session中的变量就失效了.
```

##### session的实现
>session是通过HttpSession接口实现的,同一浏览器访问多次，在这多次访问之间传递信息，就是session作用域
 - 变量的存放
  - Object HttpSession.getAttribute(String name) ：从session中获取信息
  - void HttpSession.setAttribute(String name, Object value)： 向session中保存信息
 - 获取session对象
  - HttpServletRequest.getSession()方法可以获得HttpSession对象
  - 浏览器发送第一个http请求时session即开启,浏览器关闭的时session关闭,在服务器中,如果一定的时间内客户端没有反应，则认为会话结束.
  - session在服务器中可以设置默认的作用时间,tomcat中默认超时时间是30分钟
  - vooid invalidate() 强制结束当前session


[========]

#### application
>它的有效范围是整个应用,在应用程序启动的时候生效,应用程序关闭的时候结束,在整个应用程序运行的期间都可以使用,实现的接口是ServletContext

```
指从应用启动，到应用结束(非服务器启动的时候,一个服务器可以部署多个应用程序)
此作用域的变量存活时间最长,在不进行手动删除的时候会一直有效
application作用域中的数据是共享的,如果用户甲的操作修改了application中的变量，用户乙访问时得到的是修改后的值
在，page, request, session这几个scope中数据都是完全隔离的，无论如何修改都不会影响其他人的数据
```

##### application的实现
>application作用域上的信息传递就是通过ServetContext实现的
- 变量存放
 - Object getAttribute(String name) 从application中获取信息
 - void setAttribute(String name, Object value) 向application作用域中设置信息

[========]

#### page
>page指当前页面。在一个jsp页面里有效

```
只能在当前jsp页面有效,当跳转到另一个jsp页面便失效了
```
