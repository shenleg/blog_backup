---
title: OpenWrt-旁路由设置
categories:
  - 折腾
  - OpenWrt
tags:
  - openwrt
date: 2023-06-28 03:04:48
---

# 需求

让 OpenWrt 以旁路由模式运行

# 步骤

## 1. lan 口设置

网络 - 接口，只保留 lan 口，其他全删掉

![基本设置](https://cdn.myshenle.top/images/202307021211080.png)

![DHCP设置](https://cdn.myshenle.top/images/202307021212256.png)

![高级设置](https://cdn.myshenle.top/images/202307021223345.png)

![物理设置](https://cdn.myshenle.top/images/202307021223315.png)




## 2. 防火墙设置

![常规设置](https://cdn.myshenle.top/images/202307021218799.png)

![防火墙规则](https://cdn.myshenle.top/images/202307021225109.png)

```
iptables -t nat -A PREROUTING -p udp --dport 53 -j REDIRECT --to-ports 53
iptables -t nat -A PREROUTING -p tcp --dport 53 -j REDIRECT --to-ports 53
[ -n "$(command -v ip6tables)" ] && ip6tables -t nat -A PREROUTING -p udp --dport 53 -j REDIRECT --to-ports 53
[ -n "$(command -v ip6tables)" ] && ip6tables -t nat -A PREROUTING -p tcp --dport 53 -j REDIRECT --to-ports 53

iptable -t nat -I PREROUTING -j MASQUERADE
iptables -t nat -I POSTROUTING -j MASQUERADE
```



# 参考

* [OpenWrt旁路由设置教程_秋之颂的博客-CSDN博客](https://blog.csdn.net/weixin_42708321/article/details/124720849)
