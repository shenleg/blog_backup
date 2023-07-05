---
title: OpenWrt-ZeroTier配置
categories:
  - 折腾
  - OpenWrt
tags:
  - openwrt
  - zerotier
date: 2023-07-02 17:11:48
---

# 需求

通过在 OpenWrt 搭建 ZeroTier 客户端，可以随时随地访问任意内网设备

# 步骤

## 1. 安装 ZeroTier 插件

![iStore安装](https://cdn.myshenle.top/images/202307021840983.png)

## 2. 加入网络

![加入网络](https://cdn.myshenle.top/images/202307021841426.png)

## 3. 授权配置

![授权](https://cdn.myshenle.top/images/202307021843454.png)

![路由表设置](https://cdn.myshenle.top/images/202307021845144.png)

## 4. OpenWrt 配置

![查看网卡](https://cdn.myshenle.top/images/202307021846091.png)

![创建接口](https://cdn.myshenle.top/images/202307021847278.png)

![防火墙配置](https://cdn.myshenle.top/images/202307021849486.png)

![配置端口放行1](https://cdn.myshenle.top/images/202307021850704.png)

![配置端口放行2](https://cdn.myshenle.top/images/202307021852299.png)

## 5. 验证

![控制台查看](https://cdn.myshenle.top/images/202307021855214.png)

# 参考

* [ZeroTier实现内网穿透、异地组网 (baidu.com)](https://baijiahao.baidu.com/s?id=1750252316980351363&wfr=spider&for=pc)
* [Zerotier，内网穿透神器，远程办公时代的生产力工具 (baidu.com)](https://baijiahao.baidu.com/s?id=1742540337226427902&wfr=spider&for=pc)
* [ZeroTier实现内网穿透详细教程，其实5分钟就可以搞定](https://blog.csdn.net/weixin_44786530/article/details/128283075)
