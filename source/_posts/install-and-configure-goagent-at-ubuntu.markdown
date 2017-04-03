---
tags: [IT,ubuntu]
date: 2014/07/17 00:44:05
title: 在Ubuntu环境安装配置GoAgent
---


### 离开校园网ipv6这么好的教育网之后，google和github都不能访问，需要翻墙，由于本人的博客之前搭建在ubuntu环境下，更新博客内容都要git。如github在外面普通AD下几乎是不能访问，所以goAgent来翻墙完成git的任务。

<!--more-->

### 因为之前在windows下用过goagent翻墙，所以已经注册过google application ID,如果没有的话就去注册一个，用个人的gmail邮箱，来完成，按照流程一步步点就行,<a href="https://www.x-berry.com/goagent/" target="_blank">具体流程参考</a>。不过现在大陆这边的AD连google都访问不了，除非是教育网ipv6才可访问google，或者你用人家的机子翻墙注册。

<br/>

### 记住自己的google application ID, Gmail， Gmail的password，之后有用。下载goagent，然后解压，之后打开local文件夹

    $cd local
    
### ls -al 就看到有个proxy.ini的文件，编辑他：

    $gedit proxy.ini 
    
### 改［gae］里面的appid变为你刚才在google注册的 application  ID。

### 然后返回goagent的目录，打开server，
    
    $cd server & python uploader.zip
    
### 完成python服务器端上传，便会看到一个头部信息，会显示你刚输入的app_id信息等，其实就是proxy.ini中的[gae]信息。之后会提示你输入Gmail 和 your Gmail password.
<br/>
 <img src="http://ww2.sinaimg.cn/mw1024/67804861tw1eif61dkr9aj20i10bkjta.jpg" width="700"/>
<br/>
<br/>

# 布置完成！！！

### 现在翻墙git， 打开local文件夹,输入命令：

    $ python proxy.py

<br/>
 <img src="http://ww1.sinaimg.cn/mw1024/67804861tw1eif61dzuqwj20go04pgmb.jpg" width="700"/>
<br/>
<br/>
### 因为github是使用https协议，对于goagent来说，需要先将安装证书，在Linux下，直接增加到   /etc/ssl/certs/ca-certificates.crt  。。如： 

    # cat CA.crt >> /etc/ssl/certs/ca-certificates.crt

### 即可.

### 然后完成各种git命令:

    $ https_proxy=127.0.0.1:8087 git .....
    

<br/>
Reference:<a href="https://www.evernote.com/shard/s44/sh/c1082cf7-0afc-4bd2-a066-e3c8108c0c4a/dade7194e0d74ce1183d13641e72fd4c" target="_blank">goagent 翻墙使用 github 进行git clone</a>
 * * *
