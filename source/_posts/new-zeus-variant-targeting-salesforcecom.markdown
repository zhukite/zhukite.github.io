---
tags: [IT]
date: 2014/02/23 16:43:59
title: Zeus木马新变种感染SaaS厂商Salesforce.com
---

### Zeus木马以往是攻击银行网站（你懂的，钱嘛），现在第一次针对SaaS（软件即服务）的应用进行攻击，其中最早开启SaaS模式的厂商salesforce的一名雇员的家庭电脑近日受到新变种的zeus木马感染。攻击的手法也很有巧妙，绕过避开了公司的安全监控，在该雇员的家庭电脑实施感染攻击。
<br/>
### adollom实验团队称这攻击方式是下地雷，当攻击者埋下“地雷”在这位公司雇员的不受公司控制的个人设备里来获取公司的资源信息，攻击者现在绕过传统的安全防范措施，等待感染者连接公司*.my.salesforce.com，通过这个被感染的用户的设备来盗取公司数据。这次zeus攻击是利用了一旦用户已经通过身份验证，便合理地建立终端用户和salesforce.com的互相信任关系这个条件。This is not an exploit of a Salesforce.com vulnerability（所以说为条件，不是漏洞）。
<!--more-->
<br/>
### 事件发生过程：在一个短周期时间内，单个用户执行数百视图操作这么个不寻常的行为被检测到，
<br/>
### 分析：审计日志的快速分析表明,主要是使用的设备在周末和晚上和是一个Windows XP机器运行一个旧版本的IE。长话短说:这是员工的个人拥有电脑,他们不时被使用(周末和晚上加班)补上工作。

### 　进一步的调查揭示了缺失的一个环节——这宙斯变种被配置为检测Salesforce.com经过身份验证的会话(* .my.salesforce.com)而不是银行网站。

### 本次攻击原因的调查还在进行中，。。。。。
<br/>
### 总结：

 1.这次袭击的目标是一个电脑公司控制之外(在本例中,它是一个家庭的电脑）。

 2.SaaS的世界里,有三个主要的参与者:SaaS供应商提供服务,公司购买服务和终端用户使用它。SaaS供应商安全收到大量的关注,大多数企业SaaS提供商,比如Salesforce.com,与先进的网络安全控制高度安全的组织。但SaaS用户和使用的安全性很大程度上落在了下面的客户共同责任模型。意料之中的是,用户是最薄弱的一环。他们访问公司资源以外的范围,可以很容易地利用。虽然有些人可能认为最简单的解决方案是简单地禁止使用SaaS,大多数SaaS应用程序默认是允许任何地方/任何设备访问没有标准化的用户活动监控和异常行为检测。

<br/>
### 银行系统保证用户安全上给出来一些参考，毕竟他是最早受到zeus攻击，原则是：假设所有PC会受到感染。。SaaS提供商必须假定用户设备受损和部署相关的安全控制以及更好的检测和预防能力。关键要普及用户IT安全意识，升级操作系统。


Reference参考：
<br/>
1、<a href="http://www.adallom.com/blog/a-new-zeus-variant-targeting-salesforce-com-accounts-research-and-analysis/" target="_blank">A new Zeus variant targeting Salesforce.com – Research and Analysis</a>

2、<a href="http://krebsonsecurity.com/2012/07/eu-to-banks-assume-all-pcs-are-infected/" target="_blank">EU to Banks: Assume All PCs Are Infected</a>

----------------------------------------------------
