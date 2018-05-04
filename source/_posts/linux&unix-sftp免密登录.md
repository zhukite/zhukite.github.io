---
title: linux&unix-sftp免密登录
tags: [IT]
date: 2018-05-04
---

sftp user@ip

发起连接方 把自己的公钥内容添加到 被连方的$HOME/.ssh/authorized_keys里

在配置ssh自动传输的时候注意，

.ssh目录的属主、属组使用当前用户与用户组，
.ssh目录的权限请保持700，
authorized_keys的权限为644，
id_rsa的权限为600，
id_rsa.pub的权限为644，
同时检查用户$HOME目录权限必须为755。
