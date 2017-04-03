---
tags: [IT]
date: 2014/12/12 17:25:43
title: using Koding edit static blog in the cloud
---

## 今天发现一个神器<a href="https://koding.com" target="_blank">Koding</a>，谁知人家一年前已经在用了，看人家博客（大陆的台湾的都有）写的中文用法介绍都是1月的事情，以致这神器已经更新了不少，很多东西还是看英文文档才能跟进操作。实在惭愧！

<br/>

## 其实有个问题已经困扰我大半年了，就是静态博客比起 Wordpress 这类博客的一个不足是需要先配置好整个博客环境才能编写和预览博客。以我使用nikola作为博客引擎为例，为了写一篇博客，需要在自己电脑（在虚拟机里的Ubuntu）安装配置Nikola、markdown、retext、git等，认真烦！想对已发布的文章改少少内容，除非每台机器都配合这个环境，否则我只能打开自己的电脑去修改。所以我一直想找个可以在浏览器在线编辑静态博客的工具，就像wordpress那么方便，只需打开浏览器完成文章的编辑发布。

<br/>
 <img src="http://ww4.sinaimg.cn/mw1024/67804861gw1en7gaek7ezj21690min4p.jpg" width="700"/>
<br/>
<br/>

## Koding，在<a href="http://zh.wikipedia.org/wiki/Koding" target="_blank">wikipedia</a>里吹他是PaaS的云计算平台的网络应用，果然do完后翻唔到转头，再也不用烦恼。

<br/>

## 原理其实就是把整个本地的nikola搬到“云端”的vms，在远端的部署方式与在 Linux 上基本一致。按照自己写过的<a href="http://zhukite.github.io/posts/use-nikola-to-build-a-blog-at-ubuntu-and-mount-on-gitpage.html" target="_blank">nikola配置步骤和手册</a>配置。

<br/>

## 由于 Koding 开放了端口，因此也可以用本地的浏览器预览你正在编辑的文章。比如， 输入命令

    nikola serve -a 0.0.0.0 -p 8080
    
    
## 打开nikola 的端口号是8080，那么可以访问 http://你的账户名.koding.io:端口号/ 预览在该主机编辑的网站。已经不用大半年前那种访问 http://vm-主机号.你的账户名.koding.kd.io:端口号/ 来预览了！

<br/>
 <img src="http://ww3.sinaimg.cn/mw1024/67804861gw1en7gkfkru8j20le0ee0wp.jpg" width="700"/>


### 还有SSH，FTP等功能以及在线编程等等，有待学习发掘！

 * * *
