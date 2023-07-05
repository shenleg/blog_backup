---
title: ZeroTier-创建网络
categories:
  - 折腾
  - 内网
tags:
  - zerotier
date: 2023-07-02 17:11:48
---

# 需求

搭建虚拟局域网，随时随地访问任何设备、任何内网资源。比起直接内网穿透更安全，但是速度慢

# 步骤

## 1. 注册账号，创建虚拟网络

登录官网注册账号：[ZeroTier | Global Area Networking](https://www.zerotier.com/)

![创建网络](https://cdn.myshenle.top/images/202307021715223.png)

![网络配置](https://cdn.myshenle.top/images/202307021720896.png)

## 2. 配置网段

![路由网段配置](https://cdn.myshenle.top/images/202307021718542.png)

## 3. 授权设备

![授权设备](https://cdn.myshenle.top/images/202307021722074.png)

## 4. 测试

手机安装 ZeroTier 客户端，加入网络

![手机设置](https://cdn.myshenle.top/images/202307021727050.png)

此时便可以访问加入此网络的其他设备，输入分配的 IP 即可

# 参考

* [ZeroTier实现内网穿透、异地组网 (baidu.com)](https://baijiahao.baidu.com/s?id=1750252316980351363&wfr=spider&for=pc)
* [Zerotier，内网穿透神器，远程办公时代的生产力工具 (baidu.com)](https://baijiahao.baidu.com/s?id=1742540337226427902&wfr=spider&for=pc)
* [ZeroTier实现内网穿透详细教程，其实5分钟就可以搞定](https://blog.csdn.net/weixin_44786530/article/details/128283075)
