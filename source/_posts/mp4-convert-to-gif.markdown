---
tags: [IT,ubuntu] 
date: 2014/02/13 17:31:23
title: mp4 convert to gif
---


## 动态GIF图片现在复苏了，不少在线分享和社交网络网站都开始支持动态GIF图片，由于在消费和共享上的容易，GIF的动画已经成为主流互联网文化的一部分了。下面介绍一下在Linux使用ffmpeg把自己旅行时录制的mp4格式的视频文件转换gif动态图。
<!--more-->

<br/>

### 首先，安装ffmpeg，我的操作系统是Ubuntu 12.04 ，指令是下面：

    $ sudo apt-get install ffmpeg
    
    
### 如果你的操作系统别的Linux发行版，请参考<a href="http://xmodulo.com/2013/06/how-to-install-ffmpeg-on-linux.html" target="_blank">How to install FFmpeg on Linux</a>

<br/>

### 后来发现不行，那个网站老是fetch不到，一直404，只好下源代码编译安装
### 使用git克隆ffmpeg源代码的地址：

    git clone git://source.ffmpeg.org/ffmpeg.git ffmpeg
    

### 另外，ffmpeg编译时需要使用yasm，如果系统中没有安装，可以通过下面的命令来安装：

    sudo apt-get install yasm
   
    
<br/>    
### 上述的编译工具安装好后，就可开始编译ffmpeg了。

### ffmpeg是采用autoconfig和automake等工具自动生成makefile，然后再通过make进行编译，具体的编译的过程如下：

 -  使用./configure产生makefile文件
 -  使用make进行编译
 -  使用sudo make install将ffmpeg安装到系统中，因为这个需要需要root权限。
 

### 再装个ImageMagick，发现原来已经有了，如果没有就看这里<a href="http://ask.xmodulo.com/install-imagemagick-linux.html" target="_blank">安装ImageMagick</a>
<br/>


### 弄个人的slam dunk视频,只有4秒，mp4格式的

    $ ffmpeg -t 4 -ss 00:00:00 -i slam.mp4 out1.gif 
    
### -t是时间长度，-ss是开始时间 ，这样独立的帧就输出了，时间有点长。虚拟机比较慢
<br/>

### 最后一步，

    $ convert -delay 1x20 -loop 0 out*.gif am.gif  
      
### "-delay"是控制动态速度的选项。这个选项表示在显示下一帧画面前需要等待的秒数：帧数/每秒帧数 。"-loop 0"选项表示动画的无限次循环。如果你愿意，你可以指定"-loop N"让动画只重复N次。

### 需要调节大小

    convert  am.gif -resize 50%  small-am.gif
    

### 享受技术带来的乐趣吧！:-) 奉上帕米尔高原 slam dunk
    
![](http://ww4.sinaimg.cn/mw1024/67804861gw1edi5rzwyaug208w050b2e.gif)







