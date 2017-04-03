---
tags: [IT]
date: 2014/01/19 13:41:15
title: 博客封面图片随机变换
---

### 博客头部的随机变化的封面背景，通过javascript和CSS一起实现起来并不难，下面是相应的javascript代码：<br/>
### 下面这段代码放在html的头部head中，

    <script language="JavaScript" type="text/javascript" >
    	var imgNameList=new Array();
    	imgNameList.push("/1000x226_01.JPG");
    	imgNameList.push("/1000x226_02.JPG");
    	imgNameList.push("/1000x226_03.JPG");
    	imgNameList.push("/1000x226_04.JPG");
    	imgNameList.push("/1000x226_05.JPG");
    	imgNameList.push("/1000x226_06.JPG");
    </script>

### 下面这段放在html的body中,

    <script>
    document.write("<style>#aaa {background: url("+imgNameList[parseInt(Math.random()*imgNameList.length)]+");}<\/style>");
    </script>
<!--more-->
<br/>
### 接下来对我的那几张图片进行介绍一下,拍得比较满意就贴出来当封面背景照片：
<br/>
* 帕米尔高原 昆仑山 新疆
<img src="http://ww2.sinaimg.cn/large/67804861gw1ecotm5xyqij20rs06ajtw.jpg" width="700"/>
<br/><br/>
* 丙察察线出目诺村的第一个山口森林 西藏
<img src="http://ww4.sinaimg.cn/large/67804861gw1ecotm6avu2j20rs06a40a.jpg" width="700"/>
<br/><br/>
* 羊卓雍错 西藏
<img src="http://ww3.sinaimg.cn/large/67804861gw1ecotm6dqlqj20rs06a0ua.jpg" width="700"/>
<br/><br/>
* 天山 哈希勒根达坂 新疆
<img src="http://ww1.sinaimg.cn/large/67804861gw1ecotm6op7gj20rs06ajt6.jpg" width="700"/>
<br/><br/>
* 南迦巴瓦峰 西藏
<img src="http://ww1.sinaimg.cn/large/67804861gw1ecotm6rk9rj20rs06aq4g.jpg" width="700"/>
<br/><br/>
* 白居寺后山 江孜 西藏
<img src="http://ww1.sinaimg.cn/large/67804861gw1ecotm6yia6j20rs06aq4u.jpg" width="700"/>
* * *
