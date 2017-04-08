---
title: How to Config Travis-CI
tags: [IT]
---

Github 提供的Personal Access Token与帐号密码以及SSH Keys同样具有Github写入能力，因此只要使用Travis CI提供的加密工具来加密这个Token即可。

### 方案原理

Travis CI使用一对Key Pair中的Public Key加密你提供的github Token得到一个Secure Token（将它写在 .travis.yml 中，而在Build的时候Travis会使用Private Key解密Secure Token获取最初提供的Github Personal Access Token。

### 具体的操作步骤：

1、生成一个Github Personal Access Token。前往 Github 帐号 Settings 页面，在左侧选择 Personal Access Token，然后在右侧面板点击 “Generate new token” 来新建一个 Token。需要注意的是，创建完的 Token 只有第一次可见，之后再访问就无法看见（只能看见他的名称），因此要保存好这个值。

2、使用Travis CI命令行工具加密 GitHub 的 Personal Access Token。
这个工具是一个gem包，因此需要Ruby环境，Ubuntu等系统下面，执行命令:

    apt-get isntall ruby
    apt-get isntall ruby-dev。

3、安装 Travis CI 命令行工具

    gem install travis
 
4、加密 Personal Access Token

    travis encrypt -r <GitHub用户名>/<GitHub仓库名(记得不带.git的) > GH_TOKEN=XXX
 
5、将这条命令输出的结果就是secure token，将它复制到 .travis.yml 文件下：

    env:
      global:
        - GH_REF: github.com/<GitHub用户名>/<GitHub仓库名>.git
        - secure: "XXXXXX"
    
 * * *
