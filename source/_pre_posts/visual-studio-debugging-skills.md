---
title: visual studio调试技巧
date: 2017-09-14 21:09:00
categories:
 - skill
tags:
 - visual studio
 - tools
 - skill
---

### 查看utf8编码的字符串
content.operator[](1).c_str(), s8

### 只调试部分代码
以release模式编译其他所有代码，修改部分cpp的编译选项为debug状态。

### 调试服务器代码
采用[Poco](pocoproject.org/index.html)或者[libevent](http://libevent.org/)等编写跨平台服务器端代码。  
服务器输入和输出均采用JSON的形式，HTTP POST。  
 
整个project分成3大部分，分别是：
* function core
* server core
* test core

其中，function core提供核心功能并稳定API，server core提供多并发网络输入输出，test core提供单元测试和功能调试。

调试时function core，如果需要模拟网络环境进行本地调试，则可以将参数通过本地资源进行访问。