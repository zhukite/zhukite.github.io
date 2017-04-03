---
tags: [IT,ubuntu]
date: 2014/08/24 18:56:01
title: use nikola to build a blog at ubuntu and mount on gitpage
---


## 好记性不如烂笔头，还是记录下整个静态博客搭建在github的流程。

### 我用的OS是ubuntu12.04，先安装python-pip，python-dev，在ubuntu安装很简单，输入

    sudo apt-get install python-pip 
    sudo apt-get install python-dev 

### 就可以。 按照nikola执行

    pip install nikola

### 注意：可能在执行安装nikola操作的时候会出现libxml/libxslt errors的报错。
### 那就需要先安装libxml2-dev和libslt1-dev,

    sudo apt-get install libxml2-dev
    sudo apt-get install libxslt1-dev

### 我的实际情况是在去年装的版本是nikola 6.0.1版本，现在（2014.8.23）nikola版本是7.0.1了，导致我原来的博客主题themes一些文件和变量发生变化，在进行nikola build的时候报错不能执行下去。

### 所以将version 6.0.1的nikola安装包git上去我的一个repo那里。

### 按照前面把libxml2-dev和libslt1-dev安装好后，执行nikola的安装，需要加sudo权限

    sudo pip install https://github.com/zhukite/nikola-install/archive/master.zip

### nikola安装完成！因为我原来一些post是用markdown写的，所以要装多个附加依赖包，
    sudo pip install nikola markdown
    
### 接下来就新建一个文件夹，在里面新建个website;
    nikola init

### 然后新建一个post，
    nikola new_post -f markdown 

### 编译则是nikola build; 
### 本地查看网站效果，可用 nikola serve, 使用下面地址浏览 http://localhost:8000 。

### Nikola操作手册有详细描写：<a href="http://getnikola.com/handbook.html" target="_blank">The Nikola Handbook</a>。

### nikola build后的网站展示的内容是放在output,最后，只要把mysite下面的output文件夹，push到GitHub上面即可。


================================================================================

### 在github注册一个帐号，顺便验证（verify）用户名，不然上传的东西没显示，网站出现404. 然后new 一个repo，命名username.github.io,(例如：zhukite.github.io).

### nikola build后的网站展示的内容是放在output,所以, cd output, 

### 先初始化 git init 。

### 本地local branch默认是master，git add --all, git commit -m "first commit", 这样把output文件夹下所有文件都放在本地分支的master。

### 接下来指定remote branch例如我的： 
    git remote add origin https://github.com/zhukite/zhukite.github.io.git

### 再把local branch 的文件push到remote branch：
    git push -u origin master
### 提示输入你的github帐号和密码。

### 打开浏览器输入xxxxxxx.github.io，就看到刚建的网站出来见人了～～


 * * *
