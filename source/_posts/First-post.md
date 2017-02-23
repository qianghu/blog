---
title: 如何直接将域名指向Github Pages呢?
date: 2017-02-23 17:58:34
tags: Github
---
众所周知,我们可以在Github Pages上搭建自己写的页面.那我们如何直接将域名指向Github Pages呢?
如果不知道怎么搭建博客和如何使用Github Pages的话,可以参考大神写的[开博之篇](http://stevenqiang.online/2017/02/23/first_blog/)!
## 前提
我们先得有一个域名,从网上选一个心仪的域名进行购买.

## 域名解析
我们需要将你在Github上创建的Github Pages的域名 xxx.github.io进行查询,得到一个IP地址.

``` bash
$ ping xxx.github.io
PING github.map.fastly.net (151.101.100.133): 56 data bytes
64 bytes from 151.101.100.133: icmp_seq=0 ttl=53 time=156.497 ms
--- github.map.fastly.net ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 144.956/150.726/156.497/5.771 ms
```
从ping指令得到一个IP地址 151.101.100.133, 将这个IP地址记录下来
在域名解析下进行设置
添加一个记录类型为A,主机记录为www,解析线路默认,记录值为151.101.100.133的记录
再添加一个记录类型为A,主机记录为@,解析线路默认,记录值为151.101.100.133的记录

## Github解析
在Github的xxx.github.io项目,进入【Settings】标签页,在【Custom domain】功能中,将申请的域名写进去
