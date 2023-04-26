---
title: .NET Framework Http Request
author: Hubert
date: 2023-02-24
category: .NET
layout: post
---

### 1.请求方式

* 在.NET Framework中，可以使用以下类库或方法来发起HTTP请求：

* HttpClient：这是一个新的HTTP客户端类，是从.NET Framework 4.5版本开始引入的，它提供了异步操作和更好的性能。建议使用较新。
* HttpWebRequest：使用该类可以创建一个HTTP请求，可以设置请求的参数和发送请求。
* WebClient：这是一个简单的HTTP客户端类，可以使用该类发送HTTP请求并接收响应数据。
* WebRequest：WebRequest是HttpWebRequest和FtpWebRequest的基类，它提供了一些公共属性和方法，例如：请求和响应超时、身份验证和代理等等。
